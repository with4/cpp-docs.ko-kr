---
title: 컴파일러 경고 (수준 4) C4670 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4670
dev_langs:
- C++
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9bec30fff715984073aa3061979fff11923f0bf8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33315362"
---
# <a name="compiler-warning-level-4-c4670"></a>컴파일러 경고(수준 4) C4670
'identifier': 기본 클래스에 액세스할 수 없습니다.  
  
 **try** 블록에서 throw되는 개체의 지정된 기본 클래스에 액세스할 수 없습니다. Throw되는 경우 개체를 인스턴스화할 수 없습니다. 기본 클래스가 올바른 액세스 지정자와 함께 상속되는지 확인합니다.  
  
 다음 샘플에서는 C4670을 생성합니다.  
  
```  
// C4670.cpp  
// compile with: /EHsc /W4  
class A  
{  
};  
  
class B : /* public */ A  
{  
} b;   // inherits A with private access by default  
  
int main()  
{  
    try  
    {  
       throw b;   // C4670  
    }  
    catch( B )  
    {  
    }  
}  
```