# iRonArithmetic2
Arithmetic 2 / 算法题 2

## 题目：输入一个字符串，把字符串中的空格替换成 %20 

<pre><code>

void ReplaceBlank (char string[])
{
    if (string == NULL) {
        return;
    }
    
    int originalLength = 0, numberOfBlank = 0, i = 0;
    
    /* 
     *  遍历一次 ，获得字符串的原长、空格的数量
     */
    while (string[i] != '\0') {
        ++ originalLength;
        if (string[i] == ' ') {
            ++ numberOfBlank;
        }
        ++i;
    }
    
    /* 新的字符串的长度为：原长+空格数*2 */
    int newLength = originalLength + numberOfBlank * 2;
    
    
    /* 原字符串的尾部 */
    int p0 = originalLength;
    /* 新字符串的尾部 */
    int p1 = newLength;
    
    /*
     *  从字符串的尾部开始拷贝，遇到空格就替换成%20，直至两个p0、p1两个指针相等 
     *
     */
    while (p0 >= 0 && p1 > p0) {
        /* 遇到空格 */
        if (string[p0] == ' ') {
            string[p1--] = '0';
            string[p1--] = '2';
            string[p1--] = '%';
        }
        else {
            string[p1--] = string[p0];
        }
        
        --p0;
    }
    
}
</code></pre>
