---
title: "반복기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "반복기 규칙"
  - "표준 C++ 라이브러리, 반복기 규칙"
ms.assetid: 2f746be7-b37d-4bfc-bf05-be4336ca982f
caps.latest.revision: 12
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 반복기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

반복기는 STL 컨테이너에 있는 요소를 반복하고 개별 요소에 대한 액세스를 제공할 수 있는 개체입니다.  STL 컨테이너는 모두 반복기를 제공하므로 요소가 저장되는 컨테이너 형식을 확인하지 않고도 알고리즘에서 표준 방식으로 해당 요소에 액세스할 수 있습니다.  
  
 begin\(\) 및 end\(\)와 같은 멤버 및 전역 함수와 as \+\+ 및 \-\- to와 같은 연산자를 명시적으로 사용하여 반복기를 사용함으로써 앞으로 또는 뒤로 이동할 수 있습니다.  range\-for 루프 또는 \(일부 반복기 형식에 대한\) 아래 첨자 연산자 \[\]에 반복기를 암시적으로 사용할 수도 있습니다.  
  
 STL에서 시퀀스 또는 범위의 시작 부분이 첫 번째 요소입니다.  시퀀스 또는 범위의 끝 부분은 항상 마지막 요소 다음의 요소로 정의됩니다.  전역 함수 begin 및 end는 반복기를 지정된 컨테이너에 반환합니다.  컨테이너의 모든 요소에 한 일반적인 명시적 반복기 루프 모양은 다음과 같습니다.  
  
```  
  
vector<int> vec{ 0,1,2,3,4 };  
for (auto it = begin(vec); it != end(vec); it++)  
{  
    // Access element using dereference operator  
    cout << *it << " ";  
}  
```  
  
 range\-for 루프를 사용하여 이 작업을 다 간단하게 수행할 수 있습니다.  
  
```  
for (auto num : vec)  
    {  
        // no deference operator  
        cout << num << " ";  
    }  
```  
  
 반복기에는 5가지 범주가 있습니다.  범주는 증가하는 거듭제곱 순으로 다음과 같습니다.  
  
-   **출력**.  출력 반복기 `X`는 \+\+ 연산자를 사용하여 시퀀스를 순방향으로 반복하고, \* 연산자를 사용하여 요소를 한 번만 쓸 수 있습니다.  
  
-   **입력**.  입력 반복기 `X`는 \+\+ 연산자를 사용하여 시퀀스를 정방향으로 반복하고, \* 연산자를 사용하여 요소를 몇 번이고 반복해서 읽을 수 있습니다.  \+\+ 및 \!\= 연산자를 사용하여 입력 반복기를 비교할 수 있습니다.  입력 반복기의 복사본을 증가시킨 후에는 다른 복사본을 안전하게 비교하거나 역참조하거나 증가시킬 수 없습니다.  
  
-   **정방향**.  정방향 반복기 `X`는 \+\+ 연산자를 사용하여 시퀀스를 정방향으로 반복하고, \* 연산자를 사용하여 몇 번이고 반복해서 모든 요소를 읽거나 비const 요소를 쓸 수 있습니다.  \-\> 연산자를 사용하여 요소 멤버에 액세스하고 \=\= 및 \!\= 연산자를 사용하여 정방향 반복기를 비교할 수 있습니다.  정방향 반복기 복사본을 여러 개 만들어 각각을 독립적으로 역참조하고 증가시킬 수 있습니다.  컨테이너에 대한 참조 없이 초기화되는 정방향 반복기를 null 정방향 반복기라고 합니다.  Null 정방향 반복기는 항상 동일한지 비교됩니다.  
  
-   양방향.  양방향 반복기 `X`는 정방향 반복기 대신 사용할 수 있습니다.  그러나 \-\-`X`, `X`\-\- 또는 \(`V` \= \*`X`\-\-\)에서처럼 양방향 반복기를 감소시킬 수도 있습니다.  요소 멤버에 액세스할 수 있고, 정방향 반복기와 동일한 방식으로 양방향 반복기를 비교할 수 있습니다.  
  
-   **임의 액세스**.  임의 액세스 반복기 `X`는 양방향 반복기 대신 사용할 수 있습니다.  임의 액세스 반복기를 사용하면 아래 첨자 연산자 \[\]를 사용하여 요소에 액세스할 수 있습니다.  \+, \-, \+\= 및 \-\= 연산자를 사용하여 지정된 요소 수를 정방향 또는 역방향으로 이동하고 반복기 사이의 거리를 계산할 수 있습니다.  \=\=, \!\=, \<, \>, \<\= 및 \>\= 연산자를 사용하여 양방향 반복기를 비교할 수 있습니다.  
  
 모든 반복기는 할당하거나 복사할 수 있습니다.  반복기는 간단한 개체로 간주되며 종종 참조가 아닌 값으로 전달되고 반환됩니다.  또한 앞에서 설명한 모든 연산은 유효한 반복기에서 수행될 경우 예외를 throw하지 않습니다.  
  
 반복기 범주의 계층 구조는 세 가지 시퀀스를 표시하여 요약할 수 있습니다.  시퀀스에 대한 쓰기 전용 액세스의 경우 다음을 사용할 수 있습니다.  
  
```  
output iterator  
   -> forward iterator  
   -> bidirectional iterator  
   -> random-access iterator  
```  
  
 오른쪽 화살표는 “대체할 수 있음"을 의미합니다. 예를 들어 출력 반복기에 대해 호출되는 모든 알고리즘은 정방향 반복기에서 원활하게 작동해야 하지만 반대의 경우는 작동하지 *않습니다*.  
  
 시퀀스에 대한 읽기 전용 액세스의 경우 다음을 사용할 수 있습니다.  
  
```  
input iterator  
   -> forward iterator  
   -> bidirectional iterator  
   -> random-access iterator  
```  
  
 이 경우 입력 반복기는 모든 범주 중에서 가장 약합니다.  
  
 마지막으로 시퀀스에 대한 읽기\/쓰기 권한의 경우 다음을 사용할 수 있습니다.  
  
```  
forward iterator  
   -> bidirectional iterator  
   -> random-access iterator  
```  
  
 개체 포인터는 항상 임의 액세스 반복기로 사용할 수 있으므로 지정된 시퀀스에 대해 적절한 읽기\/쓰기 권한을 지원하는 경우 모든 범주의 반복기로 사용할 수 있습니다.  
  
 개체 포인터가 아닌 반복기 `Iterator`는 특수화 `iterator_traits<Iterator>`에 필요한 멤버 형식도 정의해야 합니다.  이러한 요구 사항은 공용 기본 클래스 [iterator](../standard-library/iterator-struct.md)에서 `Iterator`를 파생시켜 충족할 수 있습니다.  
  
 STL의 컨테이너 및 알고리즘에서 반복기가 어떻게 사용되는지 확인하려면 각 반복기 범주의 약속 및 제한을 이해해야 합니다.  
  
> [!NOTE]
>  range\-for 루프를 사용하여 반복기를 명시적으로 사용하지 않도록 할 수 있습니다.  자세한 내용은 [루프\(최신 C\+\+\)](http://msdn.microsoft.com/ko-kr/b1b2779c-750e-4576-a514-a84178eae9da)를 참조하세요.  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]은 이제 확인된 반복기 및 디버그 반복기를 제공하여 컨테이너의 경계를 덮어쓰지 않도록 합니다.  자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md) 및 [Debug Iterator Support](../standard-library/debug-iterator-support.md)을 참조하세요.  
  
## 참고 항목  
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)