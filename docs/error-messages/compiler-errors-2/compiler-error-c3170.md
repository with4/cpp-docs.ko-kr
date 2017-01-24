---
title: "컴파일러 오류 C3170 | Microsoft Docs"
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
  - "C3170"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3170"
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3170
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

한 프로젝트에 여러 개의 모듈 식별자를 사용할 수 없습니다.  
  
 컴파일할 때 두 개의 파일에서 각기 다른 이름을 가진 [module](../../windows/module-cpp.md) 특성이 발견되었습니다.  컴파일 당 고유한 `module` 특성을 하나만 지정할 수 있습니다.  
  
 둘 이상의 소스 코드 파일에 동일한 `module` 특성을 지정할 수 있습니다.  
  
 예를 들어, 다음과 같은 모듈 특성이 발견되는 경우 컴파일러는 C3170을 발생시킵니다. 첫 번째 코드 파일:  
  
```  
// C3170.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
int main() {}  
```  
  
 두 번째 코드 파일:  
  
```  
// C3170b.cpp  
// compile with: C3170.cpp  
// C3170 expected  
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
```  
  
 여기서, 이름이 서로 다르다는 점에 유의하십시오.