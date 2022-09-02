class Solution {
public:
    bool checkpalindrom(string &s, int i, int j){
         while (i <= j){
        if (s[i] != s[j])
        {
            return false;
        }
        i++, j--;
    }
    return true;
    }
    string longestPalindrome(string s) {
        int n=s.length();
        int a,b,c=0;
        for(int i=0; i<n; i++){
            for(int j=i; j<n; j++){
                if(checkpalindrom(s,i,j)){
                    int d=j-i+1;
                    if(d>c){
                        a=i;
                        c=d;
                    }
                } 
            }
        }
        return s.substr(a,c);
    }
};