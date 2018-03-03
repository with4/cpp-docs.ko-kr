---
title: "컴파일러 오류 C3809 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3809
dev_langs:
- C++
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 22b4406676ced6c2a96241eb15a4329d8933b777
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3809"></a>컴파일러 오류 C3809
'class': 관리되는 또는 WinRT 형식에 friend 함수/클래스/인터페이스를 사용할 수 없습니다.  
  
 관리 되는 형식 및 Windows 런타임 형식에서는 friend를 허용하지 않습니다. 이 오류를 해결하려면 관리되는 형식이나 Windows 런타임 형식 내에서 friend를 선언하지 마세요.  
  
 다음 샘플에서는 C3809를 생성합니다.  
  
```  
// C3809a.cpp  
// compile with: /clr  
ref class A {};  
  
ref class B  
{  
public:  
   friend ref class A;   // C3809  
};  
  
int main()  
{  
}  
```