# Github-Arrays
#include <iostream>
#include <vector>
#include <unordered_map>

std::vector<int> twoSum(std::vector<int>& nums, int target) {
    std::unordered_map<int, int> numToIndex;
    std::vector<int> result;

    for (int i = 0; i < nums.size(); i++) {
        int complement = target - nums[i];
        if (numToIndex.find(complement) != numToIndex.end()) {
            result.push_back(numToIndex[complement]);
            result.push_back(i);
            return result;
        }
        numToIndex[nums[i]] = i;
    }
    return result; // No solution found
}

int main() {
    std::vector<int> nums1 = {2, 7, 11, 15};
    int target1 = 9;
    std::vector<int> result1 = twoSum(nums1, target1);
    for (int index : result1) {
        std::cout << index << " ";
    }

    std::cout << std::endl;

    std::vector<int> nums2 = {3, 2, 4};
    int target2 = 6;
    std::vector<int> result2 = twoSum(nums2, target2);
    for (int index : result2) {
        std::cout << index << " ";
    }

    return 0;
}
