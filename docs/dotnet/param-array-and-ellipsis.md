---
title: "매개 변수 배열 및 가변 매개 변수(...) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "함수 오버로드, 인수 일치"
ms.assetid: 492e3f6c-1c4c-4e0c-a358-72f2d39c30be
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 매개 변수 배열 및 가변 매개 변수(...)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 오버로드된 함수 호출을 해결하기 위한 매개 변수 배열의 우선 순위가 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 Managed Extensions와 새 구문 모두 C\# 및 [!INCLUDE[vbprvb](../Token/vbprvb_md.md)]이 지원하는 매개 변수 배열을 명시적으로 지원하지 않습니다.  대신 다음과 같이 특성을 사용하여 일반 배열을 플래그 지정합니다.  
  
```  
void Trace1( String* format, [ParamArray]Object* args[] );  
void Trace2( String* format, Object* args[] );  
```  
  
 이 둘은 모두 동일하게 보이지만 `ParamArray` 특성은 C\# 또는 기타 CLR 언어에 대해 이 배열을 각 호출마다 요소의 변수 번호를 가져오는 배열로 지정합니다.  Managed Extensions와 새 구문으로 작성된 프로그램에서 동작의 차이는 Artur Laksberg가 제공한 다음 예제에서와 같이 한 인스턴스가 가변 매개 변수\(...\)를 선언하고 두 번째 인스턴스가 `ParamArray` 특성을 선언하는 오버로드된 함수 집합의 확인 방식에 있습니다.  
  
```  
int fx(...); // 1  
int fx( [ParamArray] Int32[] ); // 2  
```  
  
 Managed Extensions의 경우 가변 매개 변수\(...\)의 우선 순위가 특성보다 높습니다. 특성은 이 언어의 형식적인 측면이 아니기 때문입니다.  그러나 새 구문의 경우에는 이제 매개 변수 배열이 언어 내에서 직접 지원되며 가변 매개 변수\(...\)보다 우선 순위가 높습니다. 매개 변수 배열이 더 강력한 형식이기 때문입니다.  따라서, 아래의 호출은  
  
```  
fx( 1, 2 );  
```  
  
 Managed Extensions에서 `fx(…)`로 확인되는 반면, 새 구문에서는 `ParamArray` 인스턴스로 확인됩니다.  거의 있을 법하지 않지만 프로그램 동작이 `ParamArray` 호출 대신 가변 매개 변수\(...\) 인스턴스의 호출에 의존하는 경우 시그니처나 호출을 수정해야 합니다.  
  
## 참고 항목  
 [일반적인 언어 변경 사항](../dotnet/general-language-changes-cpp-cli.md)