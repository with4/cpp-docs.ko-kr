---
title: 컴파일러 오류 C3218 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3218
dev_langs:
- C++
helpviewer_keywords:
- C3218
ms.assetid: 0eea19e0-503e-4e07-ae8b-2cb2e95922cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6938768211a78ca2a72c78ebb03a8972e0a86a74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248273"
---
# <a name="compiler-error-c3218"></a>컴파일러 오류 C3218
'type': 형식은 제약 조건으로 사용할 수 없습니다  
  
 제약 조건에 형식에 대 한 관리 되는 클래스 또는 인터페이스에 대 한 참조 또는 값 형식 이어야 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3218 오류가 발생 합니다.  
  
```  
// C3218.cpp  
// compile with: /clr /c  
class A {};  
ref class B {};  
  
// Delete the following 3 lines to resolve.  
generic <class T>  
where T : A   // C3218  
ref class C {};  
  
// OK  
generic <class T>  
where  T : B  
ref class D {};  
```