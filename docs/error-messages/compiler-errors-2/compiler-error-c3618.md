---
title: "컴파일러 오류 C3618 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3618
dev_langs:
- C++
helpviewer_keywords:
- C3618
ms.assetid: cacc105d-4389-4cb8-ae6c-41a3622e9a86
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1389c1c556c693cd551e6bf371d6b54cb6fcbdca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3618"></a>컴파일러 오류 C3618
'function': DllImport로 표시 된 메서드를 정의할 수 없습니다  
  
 메서드를로 <xref:System.Runtime.InteropServices.DllImportAttribute> 정의에 지정 된 합니다. DLL입니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3618 오류가 발생 합니다.  
  
```  
// C3618.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[ DllImport("user32.dll", EntryPoint="MessageBox", CharSet=CharSet::Ansi) ]  // CHANGED   
void Func();   
  
void Func() {}   // C3618, remove this function definition to resolve  
```