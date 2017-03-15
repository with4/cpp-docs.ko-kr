---
title: "컴파일러 오류 C3839 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3839"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3839"
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3839
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

관리되는 또는 WinRT 형식의 맞춤 방식을 변경할 수 없습니다.  
  
 관리되는 또는 Windows 런타임 형식에서 변수의 맞춤은 CLR 또는 Windows 런타임에 의해 제어되며 [align](../../cpp/align-cpp.md)으로 수정할 수 없습니다.  
  
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