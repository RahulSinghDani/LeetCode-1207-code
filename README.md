<!-- # LeetCode-1207-code
LeetCode 1207 easy code in c++ -->
class Solution {
public:
    bool uniqueOccurrences(vector<int>& arr) {
        bool check[arr.size()];
    int arr1[arr.size()], n = 0;
    for (int i = 0; i < arr.size(); i++){ // initializing 0 in array
        check[i] = 0;
    }
    for (int i = 0; i < arr.size(); i++){
        if (check[i] == 1){continue;}
        int count = 1;
        for (int j = i + 1; j < arr.size(); j++){
            if (arr[i] == arr[j]){
                check[j] = 1;
                count++;
            }
        }
        arr1[n] = count;
        n++;
    }
    for (int i = 0; i < n; i++){
        for (int j = i + 1; j < n; j++){
            if (arr1[i] == arr1[j]){
                return 0;
            }
        }
    }return 1;
    }
};
