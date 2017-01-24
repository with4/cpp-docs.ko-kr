---
title: "컴파일러 오류 C3628 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3628"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3628"
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3628
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'base class': 관리되는 또는 WinRT 클래스는 공용 상속만 지원합니다.  
  
 관리되는 또는 WinRT 클래스를 [private](../../cpp/private-cpp.md) 또는 [protected](../../cpp/protected-cpp.md) 기본 클래스로 사용하려고 했습니다.  관리되는 또는 WinRT 클래스는 [공용](../../cpp/public-cpp.md) 액세스에서만 기본 클래스로 사용할 수 있습니다.  
  
 다음 샘플에서는 C3628을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3628a.cpp  
// compile with: /clr  
ref class B {  
};  
  
ref class D : private B {   // C3628  
  
// The following line resolves the error.  
// ref class D : public B {  
};  
  
int main() {  
}  
```  
  
 다음 샘플에서는 C3628을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3628b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class B {  
};  
  
__gc class D : B {   // C3628, private is the default access level  
  
// The following line resolves the error.  
// __gc class D : public B {  
};  
  
int main() {  
}  
```