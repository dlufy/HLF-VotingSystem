# HLF-VotingSystem

1.installation (date 20/Feb/2019)
installation of fabric is easy using vagrant and other way is to install all fabric tools then use cygwin to run the cmd
i have installed using vagrant and problem is face are
a.g++ and build-essential install error ==>> solved using link "https://gist.github.com/application2000/73fd6f4bf1be6600a2cf9f56315a2d91"
b.  error in "composer network start " due to incompatible version of composer and fabric version ==> solved by set env variable:
 FABRIC_VERSION=hlfv12
 c. encoding error due to platform difference(wrong on unix files using windows platform) in files ==>solved using cmd :
 sed -i -e 's/\r$//' youFileName.sh



#include<bits/stdc++.h>
using namespace std;
#define MOD 1000000007
int main(){
// your code goes here
	int t;
	scanf("%d",&t);
	while(t--){
		int n;
		scanf("%d",&n);
		long long ans=0;
		vector<long long> A;
		for(int i=0;i<n;i++){
			long long x;
			scanf("%lld",&x);
			A.push_back(x);
		}
		for(int i=1;i<n;i++){
			vector<long long> b;
			long long tmp=100000000000000000;
			int indx=-1;
			for(int j=0;j<A.size();j++){
				if(tmp>A[j]+A[(j+1)%A.size()]){
					indx=j;
					tmp=A[j]+A[(j+1)%A.size()];
				}	
			}
			for(int j=0;j<A.size();j++){
				if(j==indx){
					b.push_back(A[j]+A[(j+1)%A.size()]);
					j++;
				}else
					b.push_back(A[j]);
			}
			A=b;
			ans+=tmp;
		}
		printf("%lld\n",ans);
	}
}

