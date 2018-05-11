---
title: 링커 도구 오류 LNK2033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2033
dev_langs:
- C++
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d03e8d2e0502d6e3664bff05c75fffb4f4ebd5da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2033"></a>링커 도구 오류 LNK2033
'type'에 대 한 확인 되지 않은 typeref 토큰 (토큰)  
  
 형식에는 MSIL 메타 데이터에는 정의 되어 있지 않습니다.  
  
 LNK2033로 컴파일할 때 발생할 수 있습니다 **/clr: safe** MSIL 모듈에서 형식을 참조에 대 한 MSIL 모듈에서 형식에 대 한 정방향 선언 절차가 있는 경우.  
  
 형식에서 정의 해야 **/clr: safe**합니다.  
  
 자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 LNK2033 합니다.  
  
```  
// LNK2033.cpp  
// compile with: /clr:safe  
// LNK2033 expected  
ref class A;  
ref class B {};  
  
int main() {  
   A ^ aa = nullptr;  
   B ^ bb = nullptr;   // OK  
};  
```