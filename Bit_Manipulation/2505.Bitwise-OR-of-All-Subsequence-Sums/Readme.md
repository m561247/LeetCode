### 2505.Bitwise-OR-of-All-Subsequence-Sums

首先我们知道一个大方向：OR的操作越多，就有越多的bit能被置1.

因为单个元素也属于一个subsequence，所以可以将所有的nums[i]都OR起来。即如果任何一个元素的任何一个bit位上是1，那么最终答案里该bit上也一定是1.

那么如果某个bit位上，没有任何一个现成的nums[i]是1，那么怎么判定呢？因为还存在一种可能，就是某些元素（即subsequence）的加和，恰好使得在该bit位上因为进位从而置1. 我们如何知道是否存在这样的进位呢？为了判定这样的“进位”是否会发生，我们就尽可能多地进行加法操作即可。极端一点，就是将所有元素都加起来，查看这个这个过程中，该bit位上是否曾经出现过1. 如果始终都没有出现过1，那么意味着任何一个subsequence的加和也不会在该bit位产生进位的1.

所以最终的答案，就是将nums[i]和所有presum[i]进行OR操作即可。