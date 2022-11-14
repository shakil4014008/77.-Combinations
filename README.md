# 77.-Combinations
````py

class Solution:
    def combine(self, n: int, k: int) -> List[List[int]]:
        '''
        backtracking used to find all solutions, 
        exploring all potential candidate
        if the solution candidate turns to be not a solution, 
        or not the last one
        algo discards it by making some changes on 
        the previous step, backtrack and then try again
        from n = 4 numbers, choose k = 2 numbers to make combinations        
        '''
        
        def backtrack(first = 1, curr  = []):
            # if the combination is done
            if len(curr) == k: 
                output.append(curr[:])
            for i in range(first, n + 1):
                # add i into the current combination
                curr.append(i)                
                # use next integers to complete the combination
                backtrack(i + 1, curr)                
                curr.pop()
                
        output = []
        backtrack()
        return output
        
        ![image](https://user-images.githubusercontent.com/26172918/201560116-00a84f55-a33a-4e94-a4b8-d95522483f2b.png)  

````
