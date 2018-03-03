---
title: "컴파일러 오류 C3839 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3839
dev_langs:
- C++
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36aa2146c142e66e61a8d1171cd4ba3acbb7bc96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3839"></a>컴파일러 오류 C3839
관리되는 또는 WinRT 형식의 맞춤 방식을 변경할 수 없습니다.  
  
 변수의 맞춤에서 관리 되는 또는 Windows 런타임 형식은 CLR 또는 Windows 런타임이 제어 하며 수정할 수 없습니다 [맞춤](../../cpp/align-cpp.md)합니다.  
  
 다음 샘플에서는 C3839를 생성합니다.  
  
```  
// C3839a.cpp  
// compile with: /clr  
ref class C  
{  
public:  
   __declspec(align(32)) int m_j; // C3839  
};  
  
int main()  
{  
}  
```