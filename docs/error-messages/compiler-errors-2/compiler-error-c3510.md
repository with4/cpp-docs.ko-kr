---
title: "컴파일러 오류 C3510 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3510
dev_langs:
- C++
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dddfa1ed7c21f36bebdbefb0049e356bba9cdc8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3510"></a>컴파일러 오류 C3510
type_lib' 종속 형식 라이브러리'를 찾을 수 없습니다.  
  
 [no_registry](../../preprocessor/no-registry.md) 및 [auto_search](../../preprocessor/auto-search.md) 에 전달 된 `#import` 하지만 컴파일러에서 참조 된 형식 라이브러리를 찾을 수 없습니다.  
  
 이 오류를 해결 하려면 모든 형식 라이브러리와 참조 된 형식 라이브러리를 컴파일러에 사용할 수 있는지 확인 합니다.  
  
 다음 샘플에서는 C3510 오류가 생성 됩니다.  
  
 가정 하 고 다음과 같은 두 개의 형식 라이브러리 작성 된 C3510a.tlb가 삭제 또는 경로에 없습니다.  
  
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
  
 고 두 번째 형식 라이브러리에 대 한 소스 코드에는 다음을 추가 합니다.  
  
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
  
 및 클라이언트 코드:  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```