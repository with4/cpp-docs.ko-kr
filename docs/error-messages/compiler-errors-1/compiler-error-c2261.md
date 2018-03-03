---
title: "컴파일러 오류 C2261 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3907a1d270de11af82462815ce87398e10c50513
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2261"></a>컴파일러 오류 C2261
'string': 어셈블리 참조가 잘못 되었으며 확인할 수 없습니다  
  
 값에 올바르지 않습니다.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>friend 어셈블리를 지정 하는 데 사용 됩니다. 예를 들어 a.dll를 b.dll friend 어셈블리 지정 하려는 경우 지정 a.dll) (에: InternalsVisibleTo("b") 합니다. 런타임에서 b.dll a.dll (유형 제외 하 고 개인)의 모든 항목에 액세스할 수 있도록 합니다.  
  
 Friend 어셈블리 지정 하는 경우에 올바른 구문에 자세한 내용은 [Friend 어셈블리 (c + +)](../../dotnet/friend-assemblies-cpp.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2261 오류가 발생 합니다.  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```