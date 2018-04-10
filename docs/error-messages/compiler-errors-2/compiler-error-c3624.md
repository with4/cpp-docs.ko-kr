---
title: 컴파일러 오류 C3624 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3624
dev_langs:
- C++
helpviewer_keywords:
- C3624
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d6f148b2bfc0f1f43135e05b32625bf87e420a71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3624"></a>컴파일러 오류 C3624
'type':이 형식 사용 하는 'assembly' 어셈블리에 대 한 필요  
  
 코드를 컴파일하는 데 필요한 어셈블리 (참조)이 지정 되지 않았습니다. 어셈블리에 전달 된 [#using](../../preprocessor/hash-using-directive-cpp.md) 지시문입니다.  
  
## <a name="example"></a>예  
다음 샘플에서는 C3624 오류가 생성 됩니다.  
  
```  
// C3624.cpp  
// compile with: /clr /c  
#using <System.Windows.Forms.dll>  
  
// Uncomment the following 2 lines to resolve.  
// #using <System.dll>  
// #using <System.Drawing.dll>  
  
using namespace System;  
  
public ref class MyForm : public Windows::Forms::Form {};   // C3624  
```  
