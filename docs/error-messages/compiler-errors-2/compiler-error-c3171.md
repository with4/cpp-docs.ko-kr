---
title: "컴파일러 오류 C3171 | Microsoft Docs"
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
  - "C3171"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3171"
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3171
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'module': 한 프로젝트에 다른 모듈 특성을 지정할 수 없습니다.  
  
 컴파일할 때 두 개의 파일에서 각기 다른 매개 변수 목록을 가진 [module](../../windows/module-cpp.md) 특성이 발견되었습니다.  컴파일 당 고유한 `module` 특성을 하나만 지정할 수 있습니다.  
  
 둘 이상의 소스 코드 파일에 동일한 `module` 특성을 지정할 수 있습니다.  
  
 예를 들어 다음과 같은 `module` 특성이 발견되는 경우 이 오류가 발생합니다. 첫 번째 코드 파일:  
  
```  
// C3171.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];  
int main() {}  
```  
  
 두 번째 코드 파일:  
  
```  
// C3171b.cpp  
// compile with: C3171.cpp  
// C3171 expected  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];  
```  
  
 여기서, 버전 값이 서로 다르다는 점에 유의하십시오.