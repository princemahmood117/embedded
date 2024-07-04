#include<reg51.h>
void send(char x);
void main (void)
{
	TMOD = 0x20;
	TH1 = 0xFD;
	SCON = 0x50;
	
	TR1 = 1;
	send('A');
	send('S');
	send('H');
	send('R');
	send('A');
	send('R');
	send(' ');
	send('H');
	send('A');
	send('S');
	send('A');
	send('N');
	while(1);
}

void send(char x)
{
	SBUF = x;
	while(TI == 0);
	
	TI = 0;
}