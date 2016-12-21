---
title: "컴파일러 오류 C2844 | Microsoft Docs"
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
  - "C2844"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2844"
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2844
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : 'interface' 인터페이스의 멤버일 수 없습니다.  
  
 [interface class](../../windows/interface-class-cpp-component-extensions.md)에는 속성이 아닌 데이터 멤버를 포함할 수 없습니다.  
  
 인터페이스에서는 속성이나 멤버 함수 외의 다른 항목을 사용할 수 없습니다.  생성자, 소멸자 및 연산자도 사용할 수 없습니다.  
  
 다음 샘플에서는 C2844 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2844a.cpp  
// compile with: /clr /c  
public interface class IFace {  
   int i;   // C2844  
   // try the following line instead  
   // property int Size;  
};  
```  
  
 다음 샘플에서는 C2844 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2844b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
__gc __interface IFace {  
   int i;   // C2844  
   // try the following line instead  
   // __property int Size { get; set; };  
};  
```