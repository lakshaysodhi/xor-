# xor-


#include <bits/stdc++.h>
using namespace std;
#define ll long long

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    int t;
    cin>>t;
    while(t--){
        ll n;
        cin>>n;
        ll k=1;
        vector<int> num(20);
        cout<<1<<" "<<(ll)pow(2,20)<<endl;
        ll sum;
        cin>>sum;
        sum=sum-n*(ll)pow(2,20);
        ll firstbit=sum^k;
        if(firstbit%2==0){
            num[0]=1;
        }else{
            num[0]=0;
        }
        for(int i=1;i<20;i++){
            k=k<<1;
            cout<<1<<" "<<k<<flush<<endl;
            ll newsum;
            cin>>newsum;
            if(newsum==-1) return 0;
            ll diff=(sum-newsum)/pow(2,i);
            ll nof1=(n+diff)/2;
            if(nof1%2==0){
                num[i]=0;
            }else{
                num[i]=1;
            }
        }
        ll no=0;
        for(int i=0;i<20;i++){
            if(num[i]==1){
                no+=pow(2,i);
            }
        }
        cout<<2<<" "<<no<<endl<<flush;
        int verdict;
        cin>>verdict;
        fflush(stdin);
        if(verdict==-1) return 0;
    }
    return 0;
}


