#include<bits/stdc++.h>
using namespace std;
    map<char,vector<string>>m;
    vector<string>r;
    
    bool checkparenthesis(string a){
        cout << a << endl;
        vector<char>b;
        for(int i=0; i<a.size(); i++){
            if(b.size()==0){
                b.push_back(a[i]);
            }
            if(a[i]==')'&&b.back()=='('){
                b.pop_back();
            }
            else{
                b.push_back(a[i]);
            }
        }
        if(b.size()==0){
            return true;
        }
        else{
            return false;
        }
    }
    void mix(int s, int n, string a){
        if(s==n&&checkparenthesis(a)){
            r.push_back(a);
        }
        vector<string>v=m[1];
        for(int i=0; i<v.size(); i++){
            string g=v[i];
            a+=g;
            mix(s+1, n, a);
            a.pop_back();
            a.pop_back();
        }
        
    }
    vector<string> generateParenthesis(int n) {
        m[1]={"()","((","))",")("};
        mix(0,n,"");
        return r;
    }
int main() {
  int n;
  cin >> n;
  generateParenthesis(n);
}
 