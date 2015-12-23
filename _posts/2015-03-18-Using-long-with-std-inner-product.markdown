---
layout: post
title:  "Using long with std::inner_product"
date:   2015-03-18 10:36:29
categories: c++ 
---

Today, I have write a problem which using `std::inner_product` to caculate inner product of two `std::vector<int>`. The code is like followings:

    int msp( vector<int>& left, vector<int>& right )
        return inner_product( left.begin(), left.end(), right.begin(), 0 );
    }


However, I meet overflow problem. I have tried to change from `std::vector<int>` to `std::vector<long long int>`, but it doesn't work. 

After several trials, I have found if I change 0 to `0L` or `0LL`, the overflow problem is fixed. I have do some research, and, found that the prototype of `inner_product` is like this:

    template< class InputIt1, class InputIt2, class T >
    T inner_product( InputIt1 first1, InputIt1 last1, InputIt2 first2, T value );

As you can see, the type T is determined by type of parameter `value`, so to force `inner_product` using `long` or `long long int`, we must specify that type of value by using `0L` or `0LL`.

    return inner_product( left.begin(), left.end(), right.begin(), 0LL );
