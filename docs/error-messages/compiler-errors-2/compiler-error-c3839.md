---
title: 컴파일러 오류 C3839 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3839
dev_langs:
- C++
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbb5541e07d168df36bae83f81b7b8a8a7273665
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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