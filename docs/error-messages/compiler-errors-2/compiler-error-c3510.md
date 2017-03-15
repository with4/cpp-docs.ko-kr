---
title: "컴파일러 오류 C3510 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3510"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3510"
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3510
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

종속 형식 라이브러리 'type\_lib'을\(를\) 찾을 수 없습니다.  
  
 [no\_registry](../../preprocessor/no-registry.md) 및 [auto\_search](../../preprocessor/auto-search.md)를 `#import`에 전달했지만 참조된 형식 라이브러리를 컴파일러가 찾을 수 없습니다.  
  
 이 오류를 해결하려면 모든 형식 라이브러리와 참조된 형식 라이브러리를 컴파일러에서 사용할 수 있는지 확인해야 합니다.  
  
 다음 샘플에서는 C3510 오류가 발생하는 경우를 보여 줍니다.  
  
 다음과 같은 두 개의 형식 라이브러리가 빌드되어 있고 C3510a.tlb가 경로에서 삭제되었거나 없는 경우를 가정해 봅시다.  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 두 번째 형식 라이브러리에 대한 소스 코드는 다음과 같습니다.  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 클라이언트 코드는 다음과 같습니다.  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```