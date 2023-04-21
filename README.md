# next-greater-element-I
code:-
    vector<int> nextGreaterElement(vector<int>& nums1, vector<int>& nums2) {
               unordered_map<int, int> mpx;//(nums2.size());
        stack<int> st;

        for(int i = nums2.size() - 1; i >= 0; i--) {
            while(!st.empty() && st.top() <= nums2[i]) 
                st.pop();
            if(!st.empty()) 
                mpx[nums2[i]] = st.top();
            
            else mpx[nums2[i]] = -1;
            st.push(nums2[i]);
        }
        vector<int> ans;
        for(int i = 0; i < nums1.size(); i++) 
            ans.push_back(mpx[nums1[i]]);
        return ans;
    }
    int main(){
    vector<int>nums1;
    vector<int>nums2;
    cin>>nums1>>nums2;
    vector<int>v=nextGreaterElement(nums1,num2);
    for(int i=0;i<v.size();i++)
    cout<<v[i]<<" ";
    return 0;
    }
