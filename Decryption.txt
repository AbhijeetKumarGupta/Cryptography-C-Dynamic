#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
#include <string.h>

int main() {

	int zz, xx, n=0, k=0, l, j=0, as;

	char a[65] = {'.','0','9','8','7','6','5','4','3','2','1',' ','z','y','x','w','v','u','t','s','r','q','p','o','n','m','l','k','j','i','h','g','f','e','d','c','b','a','Z','Y','X','W','V','U','T','S','R','Q','P','O','N','M','L','K','J','I','H','G','F','E','D','C','B','A'};
	char b[4000];
	char d[8000];

	printf("    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
	printf("\n    WELCOME TO THE DECRYPTION TERMINAL");
	printf("\n    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
	printf("\n******************************************");
	printf("\nEnter the text you want to decrypt below:-");
	printf("\n******************************************");
	printf("\n");
	printf("---------");
	printf("\n-ENCRYPTED-");
	printf("\n---------");
	printf("\n\n");

	gets(b);

	l = strlen(b);

	int oo,o,t, le = (l - 2)/2;
	oo = atoi(&b[le]);
	if(oo<100){
	o = oo/10;
	}else if(oo>100){
	o = oo/100;
	}
	t = atoi(&b[le+1]);
	if(t>10){
		t = t/10;
	}
	as = oo;
	if(as>100){
		as = as/10;
	}
	if(as<10){
		as = (o*10)+t;
	}

	l = l-2;

	while(n <= (l+1)){

		if(b[n] == a[j]){

			if(l < 2 ){

				printf("ERROR!!\nMINIMUM CHARACTER LENGTH IS 2.\n");
				break;

			}else if(l == 26){

				if( j+l+as >= 64){

					int aa;
					aa = (j+l+as)%64;
					j = aa - l - as;

				}

				d[k] = a[j+l+as];

			}else{

				if( j+l+13+as >= 64){

					int aa;
					aa = (j+l+13+as)%64;
					j = aa - l - 13 - as;

				}

				d[k] = a[j+l+13+as];

			}

			n = n+1;
			k = k+1;
			j = -1;

		}

		j = j+1;

	}

	printf("\n");
	printf("-----------");
	printf("\n-REGULAR-");
	printf("\n-----------");
	printf("\n\n");

	xx = strlen(d);

	for(k=0;k!=xx;k++){

		if(k == le || k == (le+1)){
			continue;
		}

		printf("%c",d[k]);

	}

	scanf("\n%d",&zz);
	return 0;

}
