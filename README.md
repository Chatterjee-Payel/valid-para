# valid-para
bool valid(string s)
{
    // code here
 stack<char>st;
 for(auto x:s)
 {
     if(st.empty())
     {
         if(x==')' or x==']' or x=='}')
         {
             return 0;
         }
         else{
             st.push(x);
             
         }
     }
      else{
         if(x==')')
         {
             if(st.top()=='(')
             {
                 st.pop();
             }
             else{
                 return 0;
             }
         }
         else if(x==']')
         {
             if(st.top()=='[')
             {
                 st.pop();
             }
             else{
                 return 0;
             }
         }
         else if(x=='}')
         {
             if(st.top()=='{')
             {
                 st.pop();
             }
             else{
                 return 0;
             }
         }
         else{
             st.push(x);
         }
      }
     
 }
 if(!st.empty())
 {
     return false;
     
 }
 return true;
}
