#include<stdio.h>
#include<string.h>
#define maxn 105
int lesss(const char* s,int p,int q){
    int n=strlen(s);
    for(int i=0;i<n;i++)
        if(s[(p+i)%n]!=s[(q+i)%n])
        return s[(p+i)%n]<s[(q+i)%n];
    return 0;
}

int main(){
    int t;
    char s[maxn];
    scanf("%d",&t);
    while(t--){
        scanf("%s",s);
        int ans=0;
        int n=strlen(s);
        for(int i=1;i<n;i++)
            if(lesss(s,i,ans))ans=i;
        for(int i=0;i<n;i++)
            putchar(s[(i+ans)%n]);
        putchar('\n');
    }
    return 0;
}
