---
title: "컴파일러 오류 C3469 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3469
dev_langs: C++
helpviewer_keywords: C3469
ms.assetid: e23b0e5c-c704-4e67-a868-bf02c2055d85
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 64a82be68ec8722db40bb3f39e4898219e9e16c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3469"></a>컴파일러 오류 C3469
'type': 제네릭 클래스는 전달할 수 없습니다.  
  
 제네릭 클래스에서 형식 전달을 사용할 수 없습니다.  
  
 자세한 내용은 참조 [형식 전달 (C + + /cli CLI)](../../windows/type-forwarding-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 구성 요소를 만듭니다.  
  
```  
// C3469.cpp  
// compile with: /clr /LD  
generic<typename T>  
public ref class GR {};  
  
public ref class GR2 {};  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3466를 생성합니다.  
  
```  
// C3469_b.cpp  
// compile with: /clr /c  
#using "C3469.dll"  
[assembly:TypeForwardedTo(GR::typeid)];   // C3469  
[assembly:TypeForwardedTo(GR2::typeid)];   // OK  
```