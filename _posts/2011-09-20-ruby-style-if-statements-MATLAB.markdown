---
layout: post
title:  "Ruby type if statements in MATLAB"
date:   2011-09-20 07:54:00 -0500
categories: hack
---

I do miss Ruby type 'if' statements in MATLAB, so to overcome that I 
figured there has to be a simple way.

In ruby I could say: a = 1 if true. But in MATLAB one has to write 
three lines to get it done(I know, I can be lazy at times!). In MATLAB 
it would be:

{% highlight matlab %}
if true 
a = 1; 
end
{% endhighlight %}

To get similar statements as in Ruby I would be using a keyword 'do'. 
So in MATLAB my statements would look like :

{% highlight matlab %}
do a = 1 if true.
{% endhighlight %}

Not too bad, better than typing out three lines. So essentially, 'do' 
will be a function which will take in variable arguments and parse for 
if conditions and evaluate it for you in the caller workspace. I have 
left out the error checking. But here is the code:

{% highlight matlab %}
%/
%  Developer : Srinivas Muddana (srinivas.muddana@gmail.com)
%  All code (c)2012 Srinivas Muddana. all rights reserved
% 
% do a = a*-1 if(a<0);
% can add a ternary operator too.??
function do(varargin)
    %expr = size(2*length(varargin) -1) ;
    expr = '';
    for(ii = 1:length(varargin))
        expr = [expr ' ' varargin{ii}];
    end
    [a,b, c, d] = regexp(expr, '(.*)if(.*)');

    bodyIndexRange = c{1}(1,:);
    ifBodyStr = expr(bodyIndexRange(1):bodyIndexRange(2));
    condIndexRange = c{1}(2,:);
    ifCondStr =  expr(condIndexRange(1):condIndexRange(2));
    
    code = ['if(' ifCondStr ')' char(10) ...
            ifBodyStr ';' char(10)...
            'end' char(10)];
    evalin('caller', code);
end
{% endhighlight %}

https://gist.github.com/1222462