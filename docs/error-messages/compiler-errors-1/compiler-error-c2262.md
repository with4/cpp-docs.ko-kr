---
title: "컴파일러 오류 C2262 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2262
dev_langs:
- C++
helpviewer_keywords:
- C2262
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f569c3aa09c08b7553800d39be8ad6d50f8a5b3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2262"></a>컴파일러 오류 C2262
'attribute_specifiers': InternalsVisibleTo 선언에는 버전, 문화권 또는 프로세서 아키텍처를 지정할 수 없습니다.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성을 올바르게 지정하지 않았습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2262를 생성합니다.  
  
```  
// C2262.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262  
[assembly: InternalsVisibleTo("assembly_name ")];   // OK  
```