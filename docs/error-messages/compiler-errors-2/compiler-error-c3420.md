---
title: "컴파일러 오류 C3420 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3420
dev_langs:
- C++
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da0c47ccb08d1d4e9aa4c75fbce4d4fe8252a340
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3420"></a>컴파일러 오류 C3420
'finalizer': 종료자는 virtual일 수 없습니다.  
  
 종료자는 바깥쪽 형식에서 비가상으로만 호출할 수 있습니다. 따라서 가상 종료자를 선언하면 오류가 발생합니다.  
  
 자세한 내용은 참조 [소멸자 및 종료자에서 하는 방법: 클래스 및 구조체 정의 및 사용 (C + + /cli CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3420을 생성합니다.  
  
```  
// C3420.cpp  
// compile with: /clr /c  
ref class R {  
   virtual !R() {}   // C3420  
};  
```