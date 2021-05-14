# assignment5
class Solution { public: int subarraysDivByK(vector& A, int K) { map<int,int> map; map[0] = 1; int result = 0; int sum = 0;

    for(const auto & a: A) {
        sum += a;
        int value = 0;
        value= ((sum % K) + K) % K;
        auto it1 = map.find(value);
        if (it1 != map.end()){
             map[value]++;
        }else{
             map[value] = 1;
        }
    }      
    for(const auto & [key,_]:map)
        result += map[key] * (map[key] - 1) / 2; 
    return result;
}
}
