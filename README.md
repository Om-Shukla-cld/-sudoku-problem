#  kthy positive missing number 
class Solution {
public:
    int findKthPositive(vector<int>& arr, int k) {
        int low = 0, high = arr.size() - 1;
        
        while (low <= high) {
            int mid = low + (high - low) / 2;
            int missing = arr[mid] - (mid + 1);  // Count of missing numbers before arr[mid]

            if (missing < k) {
                low = mid + 1;  // Need to look further
            } else {
                high = mid - 1; // Narrow the search
            }
        }
        
        return  k+1+high ;
    }
};

