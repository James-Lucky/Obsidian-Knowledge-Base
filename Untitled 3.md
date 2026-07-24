# 10GB file becomes 3GB after zipping…  
So where did the 7GB go?  
  
👉 It wasn’t removed. It was compressed.  
  
⸻  
  
🧠 Core Idea:  
  
Most files contain a lot of redundant data (repetition).  
  
For example:  
Instead of storing → AAAAABBBBBCCCC  
Compression stores → A×5, B×5, C×4  
  
So the same information is stored in a shorter form.  
  
⸻  
  
⚙️ How ZIP works:  
  
ZIP uses lossless compression algorithms (like DEFLATE):  
  
👉 Finds repeated patterns  
👉 Replaces them with smaller representations  
👉 Builds a dictionary of repeating data  
  
So instead of storing full data again and again,  
it stores reference + pattern  
  
⸻  
  
🚀 Important Point:  
  
When you unzip the file,  
you get back the exact same 10GB data  
  
👉 Nothing is lost  
👉 Just encoded efficiently  
  
⸻  
  
📉 Why size reduces:  
  
* Text / logs / code → highly repetitive → compress well  
* Images / videos (already compressed) → little reduction  
  
⸻  
  
🎯 Interview Insight:  
  
Compression doesn’t “delete” data.  
It reduces redundancy by encoding patterns efficiently.  
  
Follow [@codedsoul_05](https://www.instagram.com/codedsoul_05/) ♥️ for such type of content

12w