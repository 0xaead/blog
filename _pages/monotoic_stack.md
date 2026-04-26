mono stack
-----------
Monotonic stacks are a powerful data structure pattern used to solve array problems in linear time by maintaining elements in a strictly increasing or decreasing order.

- Finding Nearest Smaller or Greater Elements (NSE/NGE)
This is the most common use case, where you need to identify the first element to the left or right that is larger or smaller than the current one.
* Logic: Use a monotonically decreasing stack to find the next greater element; as you iterate,
** if the current element is larger than the stack's top, it is the "next greater" for that top element.
	Challenges:
	Next Greater Element I: Find the next greater element in a second array for elements in a first.
	Next Greater Element II: Same as above but for a circular array, requiring two passes over the input.
	Daily Temperatures: Find how many days you must wait for a warmer temperature (a next greater element problem). 

- Calculating Maximum Area (Histogram Problems)
Used when you need to find boundaries for each element where it remains the minimum or maximum in its range. 
*	Logic: A monotonically increasing stack helps find the first smaller element to both the left and right of every bar. The width of the rectangle is determined by these two boundaries.
*	Challenges:
	Largest Rectangle in Histogram: Calculate the largest rectangle area formed by contiguous bars.
	Maximal Rectangle: Extend the histogram logic to a 2D binary matrix by treating each row as a histogram base. 

- Maintaining Lexicographical Order or Constraints
When the goal is to form the smallest or largest possible result by removing elements while maintaining relative order. 
*	Logic: Use a stack to greedily keep the smallest characters at the bottom. If the current character is smaller than the stack's top and you still have removals left, pop the top.
*	Challenges:
	Remove K Digits: Form the smallest possible number by removing digits.
	132 Pattern: Find if a subsequence exists such that 
- Range Minimum/Maximum Queries (Sliding Windows)
While often solved with a monotonic deque, the underlying principle is the same: maintaining a monotonic property to find the extreme value in a sliding range. 
 Medium +1
	Logic: Elements are added to the back, but before adding, all smaller elements are popped because they will never be the maximum in any future window that includes the new larger element.
	Challenges:
	Sliding Window Maximum: Find the maximum value in every window of size as it slides across the array.
	Sum of Subarray Minimums: Calculate the sum of the minimum of every possible subarray. 
- Visibility and Elevation (Geometric Problems)
Used for problems involving "views" or "trapping" based on height differences between elements. 
	Logic: Elements that are "blocked" by taller or shorter neighbors are removed from the stack once their boundary is reached.
	Challenges:
	Trapping Rain Water: Calculate how much water is trapped between bars.
	Buildings With an Ocean View: Identify buildings that can "see" the ocean without being blocked by taller buildings to their right. 

Here’s a pattern-recognition checklist for monotonic stack problems, but grounded in real LeetCode problems + links, so you can train your intuition directly on actual questions instead of abstract rules.
________________________________________
🧠 Tier 1 — “Instant recognition” (≈99% stack problems)
If you see these phrases, you should immediately think monotonic stack.
________________________________________
✅ 1. “Next greater / smaller element”
	Next Greater Element I
https://leetcode.com/problems/next-greater-element-i/ 
	Next Greater Element II
https://leetcode.com/problems/next-greater-element-ii/ 
	Next Greater Node in Linked List
https://leetcode.com/problems/next-greater-node-in-linked-list/ 
👉 Recognition:
“For each element, find the next element that is greater/smaller”
✔ Direct mapping to monotonic stack 
________________________________________
✅ 2. “Histogram / largest rectangle”
	Largest Rectangle in Histogram
https://leetcode.com/problems/largest-rectangle-in-histogram/ 
	Maximal Rectangle
https://leetcode.com/problems/maximal-rectangle/ 
👉 Recognition:
“Expand left/right until blocked”
✔ This is range boundary detection
________________________________________
✅ 3. “Stock span / previous greater”
	Online Stock Span
https://leetcode.com/problems/online-stock-span/ 
👉 Recognition:
“How far back can we go until condition breaks?”
________________________________________
🧠 Tier 2 — “Hidden next-greater problems” (≈80%)
These problems don’t explicitly say “next greater”, but they are exactly that.
________________________________________
✅ 4. “Wait until condition happens”
	Daily Temperatures
https://leetcode.com/problems/daily-temperatures/ 
👉 Hidden meaning:
“Next greater temperature” 
________________________________________
✅ 5. “First blocking element / visibility”
	Find Buildings With an Ocean View
https://leetcode.com/problems/find-buildings-with-an-ocean-view/ 
	Number of Visible People in a Queue
https://leetcode.com/problems/number-of-visible-people-in-a-queue/ 
👉 Recognition:
“Can see until blocked by taller element”
✔ That’s a decreasing stack
________________________________________
✅ 6. “Discount / first cheaper price”
	Final Prices With a Special Discount in a Shop
https://leetcode.com/problems/final-prices-with-a-special-discount-in-a-shop/ 
👉 Hidden meaning:
“Next smaller element”
________________________________________
🧠 Tier 3 — Contribution / subarray problems (harder to spot)
These are the ones that confuse people most.
________________________________________
✅ 7. “Sum of subarray minimum/maximum”
	Sum of Subarray Minimums
https://leetcode.com/problems/sum-of-subarray-minimums/ 
	Sum of Subarray Ranges
https://leetcode.com/problems/sum-of-subarray-ranges/ 
👉 Recognition:
“Each element contributes to many subarrays”
✔ Requires:
	previous smaller 
	next smaller 
________________________________________
✅ 8. “Maximum min-product / contribution”
	Maximum Subarray Min-Product
https://leetcode.com/problems/maximum-subarray-min-product/ 
👉 Same pattern:
Find range where element is minimum
________________________________________
🧠 Tier 4 — Greedy + stack (sequence optimization)
________________________________________
✅ 9. “Remove elements to make optimal sequence”
	Remove K Digits
https://leetcode.com/problems/remove-k-digits/ 
	Remove Duplicate Letters
https://leetcode.com/problems/remove-duplicate-letters/ 
	Smallest Subsequence of Distinct Characters
https://leetcode.com/problems/smallest-subsequence-of-distinct-characters/ 
👉 Recognition:
“Maintain best sequence while scanning”
✔ Monotonic stack + greedy
________________________________________
🧠 Tier 5 — Complex structural problems
________________________________________
✅ 10. “Rain / valley / trapping”
	Trapping Rain Water
https://leetcode.com/problems/trapping-rain-water/ 
👉 Recognition:
“Find boundaries on both sides”
________________________________________
✅ 11. “Pattern detection (132 pattern)”
	132 Pattern
https://leetcode.com/problems/132-pattern/ 
👉 Recognition:
stack used to maintain candidates for pattern
________________________________________
🔑 MASTER CHECKLIST (with real problem anchors)
Run this mentally:
________________________________________
✔ 1. “Nearest element” pattern?
	Example: Next Greater Element I
👉 YES → stack 
________________________________________
✔ 2. “Wait until condition happens”?
	Example: Daily Temperatures
👉 hidden next-greater 
________________________________________
✔ 3. “Range expansion / span”?
	Example: Largest Rectangle in Histogram
👉 left/right boundary 
________________________________________
✔ 4. “Contribution to subarrays”?
	Example: Sum of Subarray Minimums
👉 two boundaries → stack twice 
________________________________________
✔ 5. “Greedy remove previous decisions”?
	Example: Remove K Digits
👉 maintain monotonic structure 
________________________________________
✔ 6. “Elements become useless permanently”?
	Example: any of the above
👉 core monotonic stack property 
________________________________________
✔ 7. “Brute force = O(n²), but feels reducible to O(n)”?
👉 strong signal
________________________________________
🚨 Anti-pattern (avoid confusion)
If you see:
	sliding window → probably NOT stack 
	heap / priority queue → global min/max 
	DP with states → not stack 
________________________________________
🧠 Final condensed recognition rule
If a problem asks for nearest + comparison + one-pass + discard useless elements,
it is almost certainly a monotonic stack problem.
________________________________________
🚀 Practical advice (what actually works)
From real practice insight:
You won’t recognize this pattern from rules alone—you need to solve ~15–20 problems before it “clicks” 
Good—this is exactly the moment where many people feel the “gap” in understanding.
If the scan is over and elements are still in the stack, are they useless?
Short answer:
No—they’re not useless. It just means:
Their “event” (the thing you were waiting for) never happened.
What you do next depends on what the problem is asking.
________________________________________
1. What does “still in stack at the end” mean?
During scanning, elements are waiting for something like:
	“next smaller element” 
	“next greater element” 
	“right boundary” 
If they are still in the stack at the end:
They never found such an element to their right.
________________________________________
Formal meaning
For an element jstill in stack after processing all i:
∄i>j" such that condition holds" 

So its “next neighbor” is:
	undefined 
	or treated as a boundary (depends on problem) 
________________________________________
2. What to do with remaining elements?
There are 3 standard strategies, depending on the problem.
________________________________________
Case A: Assign default answer (most common)
Example: Next Greater Element
If no greater element exists:
res[j] = -1;
You can:
	either initialize with -1 
	or process remaining stack explicitly 
________________________________________
Case B: Treat as extending to array boundary
Example: Histogram (LeetCode 84)
Remaining elements mean:
Their rectangle extends to the end of the array
So we simulate a “virtual smaller element” at the end.
________________________________________
Two equivalent approaches
✔ Method 1: Add sentinel
heights.push_back(0); // forces all pops
________________________________________
✔ Method 2: Final cleanup loop
while (!st.empty()) {
    int h = heights[st.top()];
    st.pop();
    int left = st.empty() ? -1 : st.top();
    int width = n - left - 1;
    maxArea = max(maxArea, h * width);
}
________________________________________
Case C: Circular array (wrap around)
Example: Next Greater Element II
We simulate:
for (int i = 0; i < 2*n; i++)
So elements get a “second chance” to find neighbors.
________________________________________
3. Why they are NOT useless (important)
Those elements still represent:
Valid candidates that were never dominated and never resolved
They are actually:
	maximal elements in the suffix 
	or elements whose “event never triggered” 
________________________________________
4. Connection back to Pareto frontier
At the end:
The stack is the remaining Pareto frontier
These elements are:
	not dominated by anything to their right (because nothing exists) 
	still valid candidates, but with no matching partner 
________________________________________
5. General pattern (very important)
Monotonic stack problems always follow this lifecycle:
Step 1: Process elements
	push 
	pop when dominated 
Step 2: Resolve answers during pops
	when popping, we often compute something 
Step 3: Handle leftovers
	assign default 
	or compute boundary-based results 
________________________________________
6. Key insight: answers are produced at POP time
This is the most important mental shift:
The real “work” happens when elements are popped, not when they remain.
________________________________________
Example: Next Greater Element
When you pop j because of i:
res[j] = nums[i];
So:
	resolved at pop 
	leftover = unresolved → default 
________________________________________
Example: Histogram
When popping:
	you compute area using: 
	current index = right boundary 
	new top = left boundary 
Leftovers:
	right boundary = end of array 
________________________________________
7. Mathematical interpretation
Each element defines a region of influence:
(i_leftⓜ,i_right )

	left boundary: previous smaller 
	right boundary: next smaller 
If no right boundary exists:
i_right=n

So leftover elements simply have:
"open interval extending to boundary" 

________________________________________
8. Why cleanup is necessary
Because:
Some elements never encountered the condition that would trigger their resolution
So we must force resolution manually.
________________________________________
9. Clean unified template
for (int i = 0; i < n; i++) {
    while (!st.empty() && condition) {
        // resolve for st.top()
        st.pop();
    }
    st.push(i);
}

// final cleanup
while (!st.empty()) {
    // resolve remaining elements
    st.pop();
}
________________________________________
10. Final intuition
	Stack = waiting room of candidates 
	Pop = “event happens → resolve” 
	End of array = “no event happened → use boundary/default” 
________________________________________


Final takeaway (important)
----------
Elements left in the stack are not useless—they represent cases where the “trigger condition” never occurred, so their result must be derived from problem-defined boundaries or defaults.
