## **Sort 0’s and 1’s in array**

**Solution : TWO Pointer method**

## Sorting the array of 0’s 1’s and 2’s

## Dutch flag algorithm(3 pointer algorithm)

```cpp
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int low=0;
        int mid=0;
        int high=nums.size()-1;

        while(mid<=high){
            if(nums[mid]==2){
                swap(nums[mid],nums[high]);
                high--;
            }
            else if(nums[mid]==0){
                swap(nums[mid],nums[low]);
                low++;
                mid++;
            }
            else if(nums[mid]==1){
                mid++;
            }
        }
        return;
    }
};
```

## Merge 2 sorted arrays LC 88

```cpp
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int i=m-1;
        int j=n-1;
        int k= m+n-1;

       

        while(j>=0 && i>=0){
            if(nums1[i] > nums2[j]){
                nums1[k]=nums1[i];
                i--;
                k--;
            }
            else{
                nums1[k]=nums2[j];
                j--;
                k--;
            }
        }

        while(j>=0){
            nums1[k--]=nums2[j--];
        }
        

    }
};
```