---
title: "컴파일러 오류 C2397 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2397
dev_langs:
- C++
ms.assetid: b418cf5a-d50d-4a6c-98a7-994ae35046d1
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 31f2b548fd13bc7702d44ef4a6d5dc5c34a5eb3c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2397"></a>컴파일러 오류 C2397
'type_1'에서 'type_2'으로 변환 해야 축소 변환  
  
 균일 초기화를 사용 하는 경우 암시적 축소 변환을 찾았습니다.  
  
 C 언어를 사용 하면 할당 및 초기화에 암시적 축소 변환 및 많은 코드 오류의 원인인 예기치 않은 축소 하는 경우에 c + + 무늬를 따릅니다. 코드를 안전 하 게 만들 수는 c + + 표준 초기화 목록에서 축소 변환을 수행 하는 경우 진단 메시지가 필요 합니다. Visual c + +에서 진단 Visual Studio 2015에서 균일 초기화 지원 되는 구문 시작 부분을 사용 하는 경우 컴파일러 오류 C2397 됩니다. 컴파일러 생성 [컴파일러 경고 (수준 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md) 목록 또는 Visual Studio 2013에서 지원 되는 집계 초기화 구문을 사용 하는 경우.  
  
 변환 된 값 범위를 가능한 대상에 들어갈 수 있는 경우 축소 변환 해도 될 수 있습니다. 이 경우 알아야 할 컴파일러는 이상. 의도적으로 축소 변환의 만들면 명시할 의도도 표시할 정적 캐스트를 사용 하 여. 그렇지 않은 경우이 오류 메시지 코드에 버그가 있는 거의 항상 나타냅니다. 개체를 초기화 하는 형식이 입력을 처리 하기에 충분히 확인 하 여 문제를 해결할 수 있습니다.  
  
 다음 샘플은 C2397를 생성 하 고 해결 하는 방법을 보여 줍니다.  
  
```  
// C2397.cpp -- C++ narrowing conversion diagnostics  
// Compile by using: cl /EHsc C2397.cpp  
#include <vector>   
  
struct S1 {  
    int m1;  
    double m2, m3;  
};  
  
void function_C2397(double d1) {  
    char c1 { 127 };          // OK  
    char c2 { 513 };          // error C2397  
  
    std::vector<S1> vS1;  
    vS1.push_back({ d1, 2, 3 }); // error C2397  
  
    // Possible fix if you know d1 always fits in an int  
    vS1.push_back({ static_cast<int>(d1), 2, 3 });   
}  
```
