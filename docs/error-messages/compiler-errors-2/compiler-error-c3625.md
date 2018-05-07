---
title: 컴파일러 오류 C3625 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3625
dev_langs:
- C++
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a3462c3600a59c453fbde818c11b602c2254343
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3625"></a>컴파일러 오류 C3625
'native_type': 네이티브 형식은 WinRT 또는 관리되는 형식 'type'에서 파생될 수 없습니다.  
  
네이티브 클래스는 WinRT 또는 관리되는 클래스에서 상속할 수 없습니다. 자세한 내용은 참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3625 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3625.cpp  
// compile with: /clr /c  
ref class B {};  
class D : public B {};   // C3625 cannot inherit from a managed class  
```  
