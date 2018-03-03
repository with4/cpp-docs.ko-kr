---
title: "컴파일러 오류 C3238 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3238
dev_langs:
- C++
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e729e0da83638c93dd7e79a55bc0960590f93f08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3238"></a>컴파일러 오류 C3238
'type': 이 이름의 형식이 이미 'assembly' 어셈블리에 전달되었습니다.  
  
 형식 전달 구문을 통해 참조된 어셈블리에서 정의된 형식이 클라이언트 응용 프로그램에서도 정의되었습니다. 응용 프로그램 범위에서 두 형식을 모두 정의할 수 없습니다.  
  
 참조 [형식 전달 (C + + /cli CLI)](../../windows/type-forwarding-cpp-cli.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예  
 다음 샘플은 다른 어셈블리에서 전달된 형식이 포함된 어셈블리를 만듭니다.  
  
```  
// C3238.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>예  
 다음 샘플에서는 형식 정의를 포함하는 데 사용한 어셈블리를 만들지만 형식 전달 구문만 포함하지 않습니다.  
  
```  
// C3238_b.cpp  
// compile with: /clr /LD  
#using "C3238.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3238을 생성합니다.  
  
```  
// C3238_c.cpp  
// compile with: /clr /c  
// C3238 expected  
// Delete the following line to resolve.  
#using "C3238_b.dll"  
public ref class R {};  
```