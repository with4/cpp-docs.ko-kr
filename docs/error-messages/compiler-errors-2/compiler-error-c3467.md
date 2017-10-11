---
title: "컴파일러 오류 C3467 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3467
dev_langs:
- C++
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e14104c0fe67ce371f2faf5debb4a07f0c938856
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3467"></a>컴파일러 오류 C3467
'type': 이 형식은 이미 전달되었습니다.  
  
 컴파일러가 동일한 형식에 대한 2개 이상의 전달 형식 선언을 찾았습니다. 형식마다 선언은 하나씩만 허용됩니다.  
  
 자세한 내용은 참조 [형식 전달 (C + + /cli CLI)](../../windows/type-forwarding-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 구성 요소를 만듭니다.  
  
```  
// C3467.cpp  
// compile with: /LD /clr  
public ref class R {};  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3467을 생성합니다.  
  
```  
// C3467_b.cpp  
// compile with: /clr /c  
#using "C3467.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467  
```
