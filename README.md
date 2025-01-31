# Z_sim
EIS data simulation in python
- modelling of a variety of combinations of circuit elements, including CPEs and Warburg elements
- user can set an arbitrary frequency range or provide their own array of frequency values
- produces well-formatted Nyquist and Bode plots

```python
from Z_sim import Z_sim

test_1 = Z_sim(circuit="R1+R2/C2+R3/C3", 
              frequency_range=[0.000001,1000000],
              R1=10, 
              R2=5, 
              C2=1e-5, 
              R3=10, 
              C3=4e-4)

test_1.nyquist()
test_1.bode()
```
![Untitled](https://github.com/user-attachments/assets/ca9c6a17-6132-46a2-a76f-07487e60c84c)
![Untitled](https://github.com/user-attachments/assets/36134031-4e9c-4549-b7fc-af4db2e7901a)


```python
# Same as above but with CPEs
test_2 = Z_sim(circuit="R1+R2/Q2+R3/Q3", 
              frequency_range=[0.000001,1000000],
              R1=10, 
              R2=5, 
              C2=1e-5, 
              R3=10, 
              C3=4e-4, 
              a2=0.8, 
              a3=0.8)

test_2.nyquist()
test_2.bode()
```
![Untitled](https://github.com/user-attachments/assets/4fc31449-36c9-4823-a53f-72b5abf44677)
![Untitled](https://github.com/user-attachments/assets/ee33e2e0-eec6-472d-8143-ffdd10e4f7df)


```python
# Randles equivalent circuit, incorporating a Warburg element for modeling diffusion
test_3 = Z_sim(circuit="R1+C2/(W2+R2)", 
              frequency_range=[0.000001,1000000],
              R1=10, 
              R2=5, 
              C2=1e-5, 
              s2=0.02)

test_3.nyquist()
test_3.bode()
```
![Untitled](https://github.com/user-attachments/assets/de4efb97-cffa-47f0-b24e-4455e0c5dd57)
![Untitled](https://github.com/user-attachments/assets/b760705a-214c-46cb-9055-bfae9d2e678d)

