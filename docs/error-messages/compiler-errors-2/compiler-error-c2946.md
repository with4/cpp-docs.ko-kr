---
title: 컴파일러 오류 C2946 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2946
dev_langs:
- C++
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9485f424306d66514c9e919f13ff5988f8b0d1f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247073"
---
# <a name="compiler-error-c2946"></a>컴파일러 오류 C2946
명시적 인스턴스화. 'class'는 템플릿-클래스 특수화가 아닙니다.  
  
 템플릿이 아닌 클래스를 명시적으로 인스턴스화할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2946을 생성합니다.  
  
```  
// C2946.cpp  
class C {};  
template C;  // C2946  
int main() {}  
```