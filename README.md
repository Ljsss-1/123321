#高精度加法模板
#include <bits/stdc++.h>
using namespace std;
int main()
{
  string c,d;
  cin>>c>>d;
  reverse(c.begin(),c.end());
  reverse(d.begin(),d.end());
  vector<int>ans;
  int len=max(c.size(),d.size());
  int jinwei=0;
  int a,b;
  for(int i=0;i<len;i++)
  {
    a=(i<c.size())?(c[i]-'0'):0;
    b=(i<d.size())?(d[i]-'0'):0;
    int m=(a*b+jinwei)%10;
    jinwei=(a*b+jinwei)/10;
    ans.push_back(m);
  }
   if(jinwei>0)
   {
      ans.push_back(jinwei);
   }
   for(int i=ans.size()-1;i>=0;i--)
   {
        cout<<ans[i];
   }
   return 0;
}
#高精度乘法
#include <bits/stdc++.h>
using namespace std;
int main()
{
  string c,d;
  cin>>c>>d;
  reverse(c.begin(),c.end());
  reverse(d.begin(),d.end());
  int len1=c.size();
  int len2=d.size();
  vector<int>ans(len1+len2,0);
  for(int i=0;i<c.size();i++)
  {
    int a=c[i]-'0';
    for(int j=0;j<d.size();j++)
    {
      int b=d[j]-'0';
      ans[i+j]=ans[i+j]+a*b;
      if(ans[i+j]>=10)
      {
        ans[i+j+1]+=ans[i+j]/10;
        ans[i+j]=ans[i+j]%10;
      }

    }
  }
  int pos=ans.size()-1;
  while(pos>0&&ans[pos]==0)
  {
    pos--;
  }
  for(int i=pos;i>=0;i--)
  {
    cout<<ans[i];
  }
  cout<<endl;
   return 0;
}
