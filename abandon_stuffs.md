
# 第二题

应该是形参出了问题，or判断终止条件问题

n个东西分给两个人，两个人分到相同价值东西，扔掉一些，希望扔掉的最少。

``` c++
int res = INT_MAX;
void permute(vector<int> data, int abd, int loc,int sum){
    if(loc == data.size()){
        if(sum==0)   res = min(abd,res);
        return ;
    }
    else{
        permute(data,abd,loc+1,sum+data[loc]);
        permute(data,abd+data[loc],loc+1,sum);
        permute(data,abd,loc+1,sum-data[loc]);
    }
}
int main() {
    vector<int> data = {887,888,343,999,1000};
    int a = 0;
    
    int abd = 0, sum = 0;
    permute(data, 0, 0, 0);
    std::cout<< res <<std::endl;
    return 0;
}
```

# 第四题

考虑邻接表