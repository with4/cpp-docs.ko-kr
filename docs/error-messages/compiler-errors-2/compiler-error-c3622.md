---
title: 컴파일러 오류 C3622 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3622
dev_langs:
- C++
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d8c7ab18bfba899c2df41becb457ed2e7725f81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3622"></a>컴파일러 오류 C3622
'class': 'keyword' 인스턴스화할 수 없습니다 클래스 선언  
  
로 표시 된 클래스를 인스턴스화하려고 했습니다 [추상](../../windows/abstract-cpp-component-extensions.md)합니다. 로 표시 된 클래스가 `abstract` 기본 클래스로 사용할 수 있지만 인스턴스화할 수 없습니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3622 오류가 발생 합니다.  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  
