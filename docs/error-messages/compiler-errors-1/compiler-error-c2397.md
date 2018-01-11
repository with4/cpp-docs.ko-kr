---
title: "컴파일러 오류 C2397 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2397
dev_langs: C++
ms.assetid: b418cf5a-d50d-4a6c-98a7-994ae35046d1
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 315d375524884ec987fea747b1d3c20f2ad56173
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2397"></a>컴파일러 오류 C2397
'type_1'에서 'type_2'로 변환에 축소 변환이 필요  
  
 균일 초기화를 사용 하는 경우 암시적 축소 변환을 찾았습니다.  
  
 C 언어에는 할당 및 초기화에서 암시적 축소 변환을 허용 하 고 c + + 무늬 많은 코드 오류의 원인인 예기치 않은 축소 하는 경우에입니다. 코드를 더 안전 하 게 만들려면 표준 c + + 초기화 목록에서 축소 변환 발생할 때 진단 메시지를 필요 합니다. Visual c + +에서에서 진단이 Visual Studio 2015에서 지원 되는 구문에서 시작 하 여 균일 초기화를 사용 하는 경우 컴파일러 오류 C2397 합니다. 컴파일러 생성 [컴파일러 경고 (수준 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md) 목록 또는 Visual Studio 2013에서 지 원하는 집합체 초기화 구문을 사용 하는 경우.  
  
 변환 된 값의 가능한 범위는 대상에 들어갈 수 있는 알고 있는 경우 축소 변환을 허용 될 수 있습니다. 이 경우 알고 컴파일러 버전은 보다 더 합니다. 축소 변환을 의도적으로 하는 경우 확인 의도도 표시할 명시적 정적 캐스트를 사용 하 여 합니다. 그렇지 않은 경우이 오류 메시지 코드에서 버그가 있을 거의 항상 나타냅니다. 초기화 하면 개체에 있는 입력을 처리 하기에 충분히 큰 형식을 확인 하 여이 해결할 수 있습니다.  
  
 다음 샘플에서는 C2397 오류가 발생 하 고를 해결 하는 방법을 보여 줍니다.  
  
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