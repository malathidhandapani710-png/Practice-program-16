class Solution:
    def maxSubarraySum(self, arr):
        # Initialize max_so_far with the first element to handle 
        # cases where all numbers are negative.
        max_so_far = arr[0]
        current_max = arr[0]
        
        # Start from the second element
        for i in range(1, len(arr)):
            # Decision: Is it better to start a new subarray at arr[i], 
            # or extend the existing one?
            current_max = max(arr[i], current_max + arr[i])
            
            # Update the global maximum if the current subarray sum is better
            if current_max > max_so_far:
                max_so_far = current_max
                
        return max_so_far
