# XSS

******Reflected XSS******

Just entered <script>alert(1)</script> into the search box. 

******************DOM Based XSS******************

![Untitled](XSS%201f1c0d5765a84bbf885cf0c7547e2373/Untitled.png)

![Untitled](XSS%201f1c0d5765a84bbf885cf0c7547e2373/Untitled%201.png)

**************************The Client Side challenge**************************

On inspecting the source code, it became clear that any link with “alert” in it would be rejected.

![Untitled](XSS%201f1c0d5765a84bbf885cf0c7547e2373/Untitled%202.png)

So, I encoded alert(1) using an online tool and entered it. An alert box was popped.

![Untitled](XSS%201f1c0d5765a84bbf885cf0c7547e2373/Untitled%203.png)