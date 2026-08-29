# What Went Wrong, and How It Was Fixed

The original version of this model returned an 18.3% error at every latitude. This
document explains where that number came from.

---

## SUMMARY
The model was correct but the measurement was taken at the wrong moment. The pendulum was essentially doing two things at once. 

A Foucault pendulum has two separate motions occurring at the same time but on different timescales. The first motion is the fast motion which is the swing that goes back and forth.
One complete swing was evaluated at 16.0567 seconds. The second motion was the slow motion which is the precession. This is the entire plane that the pendulum swings in, rotating gradually since the Earth is turning below it. 
This is what the model was built to measure, and it is far slower than the swing.

---

## What was actually measured

Let's take a look at the original analysis line for precession:

```python 
precession = abs(np.arctan(y[-1]/x[-1])/T)
```

This equation takes where the pendulum ended up, evaluates what angle that is, and divides by the total time.
That angle contains both motions: how far the plane has rotated, and where the pendulum happened to be within its swing at that exact instant. 
We want to focus on how far the plane has rotated and not on where the pendulum was last located. So to measure only the rotation of the plane, the pendulum needs to be caught at the same point in its swing cycle where it first started.
Otherwise we get what occurred here, which is the leftover swing position being counted into the precession.

---

## The mistake in question

The simulation ran for a total time of T=100 seconds. One swing takes 16.0567 seconds, so 100 divided by 16.0567 gives 6.2279 swings. 
That is not a whole number, so the simulation ended when the pendulum was just about a quarter of the way through a swing. That offset was measured and calculated into the precession.

---

## The Clue

The clue that eventually gave it away was how every error was identical at all three latitudes, excluding the equator. Random errors vary while systematic errors do not. So getting exactly 18.3% at three different latitudes was not the behavior of a numerical error.
The Coriolis force is proportional to sin(latitude). This means the precession gets larger as latitude increases, and the leftover swing offset increases in step with it. So dividing one by the other causes the latitude to cancel out. Hence the error comes out as the same percentage every time.
This consistency was pointing towards the measurement step and not necessarily the model.

---

## Correction

```python
period = 2*np.pi*np.sqrt(64/9.8)
T = 6*period
```

Instead of stopping at a random 100 seconds, the simulation stops after six full swings are complete. The pendulum is then back at the same point in its cycle where it first started. The only angle remaining is the precession.

---

## The result

| Latitude | Modeled precession | Theoretical | Error |
|---|---|---|---|
| 0° | 0 | 0 | no precession at the equator |
| 36.2048° | 4.3e-05 | 4.3e-05 | 0.0% |
| 40.7128° | 4.74e-05 | 4.74e-05 | 0.0% |
| 82.8628° | 7.22e-05 | 7.22e-05 | 0.0% |

The modeled and theoretical values match at every latitude. Total mechanical energy remained constant to within 0.02% across all simulations which confirms the model was stable throughout.

---

## Conclusion

The physics was correct and nothing was wrong with the Runge-Kutta implementation. The parameters were all good choices. Energy was conserved the entire simulation, which is precisely what a correct integrator does.
The equations were right and the integration was right. The only error was when the photograph/sampling was taken. 
The difference is what is vital to understand since a model that produces the wrong answers for the right reasons is different from a model that is simply broken. Being able to tell the two apart is what debugging actually is.
