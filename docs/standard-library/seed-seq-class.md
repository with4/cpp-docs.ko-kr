---
title: "seed_seq 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1::seed_seq"
  - "std::tr1::seed_seq"
  - "tr1.seed_seq"
  - "seed_seq"
  - "std.tr1.seed_seq"
  - "random/std::tr1::seed_seq"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "seed_seq 클래스"
ms.assetid: cba114f7-9ac6-4f2f-b773-9c84805401d6
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# seed_seq 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

난수 엔진에 필요한 임의 시드를 공급할 수 있는 부호가 없는 정수 값의 벡터를 저장합니다.  
  
## 구문  
  
```  
class seed_seq  
{  
public:  
    // types  
    typedef unsigned int result_type;  
  
    // constructors  
    seed_seq();  
  
    template<class T>  
    seed_seq(initializer_list<T> initlist);  
  
    template<class InputIterator>  
    seed_seq(InputIterator begin, InputIterator end);  
  
    // generating functions  
    template<class RandomAccessIterator>  
    void generate(RandomAccessIterator begin, RandomAccessIterator end);  
  
    // property functions  
    size_t size() const;  
  
    template<class OutputIterator>  
    void param(OutputIterator dest) const;  
  
    // no copy functions  
    seed_seq(const seed_seq&) = delete;  
    void operator=(const seed_seq&) = delete;  
};  
```  
  
## 형식  
 `typedef unsigned int result_type;`   
시드 시퀀스의 요소 형식입니다. 32 비트 부호 없는 정수 형식입니다.  
  
## 생성자  
 `seed_seq();`   
기본 생성자로, 빈 내부 시퀀스로를 초기화 합니다.  
  
 `template<class T>`   
 `seed_seq(initializer_list<T> initlist);`   
사용 하 여 `initlist` 내부 시퀀스를 설정할 수 있습니다.  
`T` 정수 형식 이어야 합니다.  
  
 `template<class InputIterator>`   
 `seed_seq(InputIterator begin, InputIterator end);`   
제공 된 입력된 반복기 범위에 있는 모든 요소를 사용 하 여 내부 시퀀스를 초기화 합니다.  
`iterator_traits<InputIterator>::value_type` 정수 유형 이어야 합니다.  
  
## 멤버  
  
### 생성 함수  
 `template<class RandomAccessIterator> void generate(RandomAccessIterator begin, RandomAccessIterator end);`   
내부 알고리즘을 사용 하 여 제공된 된 시퀀스의 요소를 채웁니다. 이 알고리즘은 내부 시퀀스에 영향을 `seed_seq` 초기화 되었습니다.  
아무 작업도 수행 하는 경우 `begin == end`합니다.  
  
### 속성 함수  
 `size_t size() const;`   
에 있는 요소의 수를 반환 된 `seed_seq`합니다.  
  
 `template<class OutputIterator> void param(OutputIterator dest) const;`   
출력 반복기에 내부 시퀀스를 복사 `dest`합니다.  
  
## 예제  
 다음 코드 예제는 생성자 3개를 사용하여 배열에 할당된 경우 결과 `seed_seq` 인스턴스에서 출력을 생성합니다. 사용 하는 예제에 대 한 `seed_seq` 난수 생성기를 이용 하 여 확인 [\<random\>](../standard-library/random.md)합니다.  
  
```cpp  
#include <iostream>  
#include <random>  
#include <string>  
#include <array>  
  
using namespace std;  
  
void test(const seed_seq& sseq) {  
    cout << endl << "seed_seq::size(): " << sseq.size() << endl;  
  
    cout << "seed_seq::param(): ";  
    ostream_iterator<unsigned int> out(cout, " ");  
    sseq.param(out);  
    cout << endl;  
  
    cout << "Generating a sequence of 5 elements into an array: " << endl;  
    array<unsigned int, 5> seq;  
    sseq.generate(seq.begin(), seq.end());  
    for (unsigned x : seq) { cout << x << endl; }  
}  
  
int main()  
{  
    seed_seq seed1;  
    test(seed1);  
  
    seed_seq seed2 = { 1701, 1729, 1791 };  
    test(seed2);  
  
    string sstr = "A B C D"; // seed string  
    seed_seq seed3(sstr.begin(), sstr.end());  
    test(seed3);  
}  
```  
  
## 출력  
  
```Output  
  
seed_seq::size(): 0 seed_seq::param(): 5 개 요소의 시퀀스를 배열로 생성: 505382999 163489202 3932644188 763126080 73937346 seed_seq::size(): 3 seed_seq::param(): 1701 1729 1791 5 개 요소의 시퀀스를 배열로 생성: 1730669648 1954224479 2809786021 1172893117 2393473414 seed_seq::size(): 7 seed_seq::param(): 65 32 66 32 67 32 68 5 개 요소의 시퀀스를 배열로 생성 : 3139879222 3775111734 1084804564 2485037668 1985355432  
```  
  
## 설명  
 이 클래스의 멤버 함수는 예외를 throw 하지 않습니다.  
  
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)