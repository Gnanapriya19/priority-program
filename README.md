Priority programs
PROGRAM:
#include<stdio.h> #include<string.h> void main()
{
int bt[30],pr[30],np; intwt[30],tat[30],wat[30],at[30],ft[30]; int i,j,x,z,t;
float sum1=0,sum=0,awt,att; char p[5][9],y[9];
printf("\nenter the number of process"); scanf("%d",&np);
printf("\nEnter the process,burst-time and priority:");
for(i=0;i<np;i++)
scanf("%s%d%d",p[i],&bt[i],&pr[i]); printf("\nEnter the arrival-time:"); for(i=0;i<np;i++)
scanf("%d",&at[i]); for(i=0;i<np;i++)
for(j=i+1;j<np;j++)
{
if(pr[i]>pr[j])
{
x=pr[j]; pr[j]=pr[i]; pr[i]=x; strcpy(y,p[j]);
strcpy(p[j],p[i]);
strcpy(p[i],y); z=bt[j]; b t[j]=bt[i]; bt[i]=z;

}
} wt[0]=0;
for(i=1;i<=np;i++)
wt[i]=wt[i-1]+bt[i-1]; ft[0]=bt[0]; for(i=1;i<np;i++)
ft[i]=ft[i-1]+bt[i]; printf("\n\n\t\tGANTT CHART\n"); printf("\n	\n");
for(i=0;i<np;i++)
printf("|\t%s\t",p[i]);
printf("|\t\n");
printf("\n	\n");
printf("\n"); for(i=0;i<=np;i++)
printf("%d\t\t",wt[i]); printf("\n	\n");
printf("\n"); for(i=0;i<np;i++)
wat[i]=wt[i]-at[i]; for(i=0;i<np;i++)
tat[i]=wat[i]-at[i]; printf("\nPRIORITY SCHEDULING:\n");
printf("\nProcess Priority Burst-time Arrival-time Waiting-time Turnaround- time");
for(i=0;i<np;i++)
printf("\n\n%d%s\t%d\t\t%d\t\t%d\t%d\t\t%d",i+1,p[i],pr[i],bt[i],a t[i],wt[i],tat[i]);
for(i=0;i<np;i++)
sum=sum+wat[i]; awt=sum/np; for(i=0;i<np;i++)
sum1=sum1+tat[i]; att=sum1/np;
printf("\n\nAverage waiting time:%f",awt); printf("\n\nAverageturn around time is:%f",att);
}

