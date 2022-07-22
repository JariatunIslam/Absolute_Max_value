# Absolute_Max_value
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>

using namespace std;

class Difference {
    private:
    vector<int> elements;
  
  	public:
  	int maximumDifference;

	// Add your code here
        public:Difference(vector<int> ele){
                elements=ele;
                maximumDifference=-1000;
        }


        int computeDifference(){
           
                int ans;
                for(int i=0;i<(elements.size()-1);i++){
                for(int j=i+1;j<elements.size();j++){
                        ans= elements[i]-elements[j];
                        if(ans<0){
                                ans=-1*ans;
                        }
                if(maximumDifference<ans){
                    maximumDifference=ans;
                }
                }

                }
                return maximumDifference;
        }
}; // End of Difference class

int main() {
    int N;
    cin >> N;
    
    vector<int> a;
    
    for (int i = 0; i < N; i++) {
        int e;
        cin >> e;
        
        a.push_back(e);
    }
    
    Difference d(a);
    
    d.computeDifference();
    
    cout << d.maximumDifference;
    
    return 0;
}
