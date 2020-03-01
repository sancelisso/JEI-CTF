# JEI-CTF – Trivia


## Challenges
1. Trivia1
> A graphical user interface for the metasploit framework<br>
**Solution:** msfgui
2. Trivia2
>  a type of virus which self-replicate et propagate through networks <br>
**Solution:** worm
3. Trivia3
> name of the OSI layer in charge of paquet's integrity control <br>
**Solution:** Transport
4. Trivia4
>© <br>
**Solution:** copyright
5. Trivia5
> best type of data used for digital forensic <br>
**Solution:** logs
6. Trivia6
>nc <br>
**Solutiion:** netcat
7. Trivia7
> a low-level programming language with a very strong link with the architecture's machine code instructions<br>
**Solution:** assembly language
8. Trivia8
>Code:
```code
import java.util.*;
import java.math.*;

class crypter
	public static void main(String args[])
	{
		Scanner sc=new Scanner(System.in);
		int p,q,n,z,d=0,e,i;
		System.out.println("Enter the number to be encrypted and decrypted");
		int msg=sc.nextInt();
		double c;
		BigInteger msgback;
		System.out.println("Enter p");
		p=sc.nextInt();
		System.out.println("Enter q");
		q=sc.nextInt();

		n=p*q;
		z=(p-1)*(q-1);
		System.out.println("the value of z = "+z);

		for(e=2;e<z;e++)
		{
			if(gcd(e,z)==1)
			{
				break;
			}
		}
		System.out.println("the value of e = "+e);
		for(i=0;i<=9;i++)
		{
			int x=1+(i*z);
			if(x%e==0)
			{
				d=x/e;
				break;
			}
		}
		System.out.println("the value of d = "+d);
		c=(Math.pow(msg,e))%n;
		System.out.println("Encrypted message is : -");
		System.out.println(c);
                //converting int value of n to BigInteger
		BigInteger N = BigInteger.valueOf(n);
		//converting float value of c to BigInteger
		BigInteger C = BigDecimal.valueOf(c).toBigInteger();
		msgback = (C.pow(d)).mod(N);
		System.out.println("Derypted message is : -");
		System.out.println(msgback);

	}

	static int gcd(int e, int z)
	{
		if(e==0)
			return z;
		else
			return gcd(z%e,e);
	}
}
```
**Solution:** RSA
