---
title: "컴파일러 오류 C2946 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2946
dev_langs:
- C++
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 887afb5a42a7dac47b5d3b8490acf8256601f189
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
