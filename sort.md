# Sorting a vector

* Sorting an int vector
```C++ runnable
#include <bits/stdc++.h> 
using namespace std;

vector<int> Data = {3,15,-88,-3,88,103,32,1};

void printData(const string& MSG){
    cout << MSG<<" is: {";
    for (auto& d:Data) cout << d<<",";
    cout << "}"<< endl;    
}
int SortByAbs(const int& a,const int& b){
    return abs(a)==abs(b)?a<b:(abs(a)<abs(b));
}

int main()
{
    //Lambda function to sort    
    std::sort(Data.begin(),Data.end(), [](const int& a,const int& b){return a<b;});
    printData("Lambda");
    
    //Normal function. Sorting by absolute value  
    std::sort(Data.begin(),Data.end(), SortByAbs);
    printData("Function");
}
```

* Sorting an object vector by some field
```C++ runnable
#include <bits/stdc++.h> 
using namespace std;

class Pod{
public:    
    float x,y;
    float vx,vy;
    Pod(){ } //No initialization
    Pod(float _x,float _y, float _vx, float _vy){
        x=_x;y=_y;vx=_vx;vy=_vy;
    }
};

vector<Pod> Data ={
       Pod(  3.0f,1.0f,2.0f,7.0f),
       Pod( 15.0f,1.0f,2.0f,7.0f),
       Pod(-88.0f,1.0f,2.0f,7.0f),
       Pod( -3.0f,1.0f,2.0f,7.0f),
       Pod( 88.0f,1.0f,2.0f,7.0f),
       Pod(103.0f,1.0f,2.0f,7.0f),
       Pod( 32.0f,1.0f,2.0f,7.0f),
       Pod(  1.0f,1.0f,2.0f,7.0f)
    };

void printData(string MSG){
    cout << MSG<<" is: {";
    for (auto& d:Data) cout << d.x<<","; //We'll only print x for the sake of simplicity
    cout << "}"<< endl;    
}
int SortByAbsX(const Pod& a,const Pod& b){
    return abs(a.x)==abs(b.x)?a.x<b.x:(abs(a.x)<abs(b.x));
}

int main()
{
    //Lambda function to sort    
    std::sort(Data.begin(),Data.end(), [](const Pod& a,const Pod& b){return a.x<b.x;});
    printData("Lambda");
    
    //Normal function. Sorting by absolute value  
    std::sort(Data.begin(),Data.end(), SortByAbsX);
    printData("Function");
}
```
Lambda functions are more compact, aimed as small, simple functions. But harder to reuse.

Check [http://en.cppreference.com/w/cpp/algorithm/sort](http://en.cppreference.com/w/cpp/algorithm/sort) for more info
