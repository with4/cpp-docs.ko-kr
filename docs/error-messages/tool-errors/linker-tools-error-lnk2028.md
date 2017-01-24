---
title: "링커 도구 오류 LNK2028 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2028"
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK2028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"function\_containing\_function\_call" 함수에서 참조된 "exported\_function"\(decorated\_name\)  
  
 네이티브 함수를 순수 이미지로 가져오려는 경우 네이티브 컴파일과 순수 컴파일 사이에 암시적 호출 규칙이 서로 다르다는 점을 기억해야 합니다.  
  
## 예제  
 이 코드 샘플에서는 [\_\_cdecl](../../cpp/cdecl.md)을 사용하여 해당 호출 규칙을 암시적으로 지정하고 내보낸 네이티브 함수로 구성 요소를 생성합니다.  
  
```  
// LNK2028.cpp  
// compile with: /LD  
__declspec(dllexport) int func() {  
   return 3;  
}  
```  
  
## 예제  
 다음 샘플에서는 네이티브 함수를 사용하는 순수 클라이언트를 만듭니다.  그러나 **\/clr:pure**를 사용하는 경우 호출 규칙은 [\_\_clrcall](../../cpp/clrcall.md)입니다.  다음 샘플에서는 LNK2028 오류가 발생합니다.  
  
```  
// LNK2028_b.cpp  
// compile with: /clr:pure lnk2028.lib  
// LNK2028 expected  
int func();  
  
int main() {  
   return func();  
}  
```