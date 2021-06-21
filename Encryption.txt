#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <conio.h>
#include <time.h>

int main() {

	int zz, xx, n=0, k=0, l, j=0, as=0;

	double R;

	char a[65] = {'A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z','a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z',' ','1','2','3','4','5','6','7','8','9','0','.'};
	char b[4000];
	char d[8000];

	srand(time(NULL));
	R =(double)rand()/RAND_MAX;
	R = R*10000;
	as = (int)R%100;

	printf("    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
	printf("\n    WELCOME TO THE ENCRYPTION TERMINAL");
	printf("\n    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~");
	printf("\n******************************************");
	printf("\nEnter the text you want to encrypt below:-");
	printf("\n******************************************");
	printf("\n");
	printf("---------");
	printf("\n-REGULAR-");
	printf("\n---------");
	printf("\n\n");

	gets(b);

	l = strlen(b);

	if(as < 10){
		as = as+10;
	}
	d[l/2] = as/10;
	d[(l/2)+1] = as%10;

	while(n != l){
		if(k == l/2 || k == (l/2)+1){
			k++;
		}

		if(b[n] == a[j]){

			if(l<20){
				printf("ERROR!!\nMINIMUM CHARACTER LENGTH IS 20.\n");
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
	printf("\n-ENCRYPTED-");
	printf("\n-----------");
	printf("\n\n");

	xx = strlen(d);

	for(k=0;k!=xx;k++){

	if(l<2){
		 continue;
	 }
		if(k == l/2 || k == (l/2)+1){

			printf("%d",d[k]);
			continue;

		}

		printf("%c",d[k]);

	}

	scanf("\n%d",&zz);
	return 0;
}
