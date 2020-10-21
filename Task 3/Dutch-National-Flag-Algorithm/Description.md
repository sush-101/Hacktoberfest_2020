Given `N' objects coloured red, white or blue, sort them so that objects of the same colour are adjacent, with the colours in the order red, white and blue. 

The array is divided into four sections: 
<b>
>1. a[1..Lo-1] zeroes (red)  
>1. a[Lo..Mid-] ones (white)  
>1. a[Mid..Hi] unknown  
>1. a[Hi+1..N] twos (blue)  
</b>

<b>The unknown region is shrunk while maintaining these conditions</b> 
```
1. Low := 1; Mid := 1; Hi := N;  
2. while Mid <= Hi do  
   1. Invariant: a[1..Low-1]=0 and a[Low..Mid-1]=1 and a[Hi+1..N]=2; a[Mid..Hi] are unknown.  
   2. case a[Mid] in  
      • 0: swap a[Low] and a[Mid]; Lo++; Mid++  
      • 1: Mid++  
      • 2: swap a[Mid] and a[Hi]; Hi--  
```

