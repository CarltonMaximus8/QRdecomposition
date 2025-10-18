# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,m))
    u=np.empty((n,m))
    R=np.zeros((n,m))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(n):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(f"The Q Matrix is\n {Q}")
    print(f"The R Matrix is\n {R}")
    
a = np.array(eval(input()))
QR_Decomposition(a)






```

## Output
```
<img width="1046" height="768" alt="{AD6B21BF-50DB-4170-87EE-71A8284B9844}" src="https://github.com/user-attachments/assets/c3a86faa-9c59-4ff4-9e7a-c8e7c7313fbc" />
<img width="980" height="457" alt="{DC99FF9F-BB5C-40A8-8532-9C3F272E0E19}" src="https://github.com/user-attachments/assets/ffaae6c0-e9df-4f35-977b-591c2deec28b" />
<img width="983" height="795" alt="{37E9243B-A649-4536-BE5F-78A855FE0785}" src="https://github.com/user-attachments/assets/e3729d0b-99d2-4c40-b297-6ca07d9c428d" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
