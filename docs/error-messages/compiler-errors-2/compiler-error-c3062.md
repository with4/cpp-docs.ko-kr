---
title: "컴파일러 오류 C3062 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3062
dev_langs: C++
helpviewer_keywords: C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4fa921df80f0740387217ec9b295cfa90e089d54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3062"></a>컴파일러 오류 C3062
'enum': 열거자 값이 필요 하므로 내부 형식이 'type'  
  
 열거형에는 내부 형식을 지정할 수 있습니다. 그러나 일부 형식에 각 열거자에 값을 할당 해야 합니다.  
  
 열거형에 대 한 자세한 내용은 참조 하십시오. [enum 클래스](../../windows/enum-class-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C3062 오류가 생성 됩니다.  
  
```  
// C3062.cpp  
// compile with: /clr  
  
enum class MyEnum : bool { a };   // C3062  
enum class MyEnum2 : bool { a = true};   // OK  
```