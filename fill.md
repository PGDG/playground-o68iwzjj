# Remplir un tableau avec des valeurs par défaut

* Remplir un tableau static d'entiers
```C++ runnable
#include <bits/stdc++.h> 
using namespace std;

int staticArray[3000];
const int InitValue = 9990;

int main()
{
    cout << "Uninitialized Array:"<<staticArray[3000-1] << endl;
    std::fill(staticArray,staticArray+(end(staticArray) - begin(staticArray)),InitValue);
    cout << "Array filled with:"<<staticArray[3000-1] << endl;
}
```

* Remplir un vecteur d'entier de la librairie standard (vector<int>)
```C++ runnable
#include <bits/stdc++.h> 
using namespace std;

vector<int> dynArray;
const int InitValue = 9990;

int main()
{
    dynArray.resize(3000);
    cout << "Uninitialized Array:"<<dynArray.back() << endl;
    std::fill(dynArray.begin(),dynArray.end(),InitValue);
    cout << "Array filled with:"<<dynArray.back() << endl;
}
```

* Remplir un vecteur de classe (vector<class>)

Ici même si l'objet de l'initialisation est complexe, la méthode std::fill se comporte exactement de la même façon.

Utiliser memset en C++ n'est pas conseillé, en effet c'est une fonctionnalité de la librairie standard du langage C et non du C++. Dans un monde parfait personne ne l'utilise en C++:

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

vector<Pod> dynArray;
const Pod InitValue(0.6f,11.2f,0.45f,0.99f);

int main()
{
    dynArray.resize(3000);
    cout << "Uninitialized Vector:"<<dynArray.back().x<<","<<dynArray.back().y<< endl;
    std::fill(dynArray.begin(),dynArray.end(),InitValue);
    cout << "Array filled with:"<<dynArray.back().x<<","<<dynArray.back().y<< endl;
}
```
Rendez-vous [http://en.cppreference.com/w/cpp/algorithm/fill](http://en.cppreference.com/w/cpp/algorithm/fill) pour plus d'informations
