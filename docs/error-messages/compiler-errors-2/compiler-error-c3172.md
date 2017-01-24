---
title: "컴파일러 오류 C3172 | Microsoft Docs"
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
  - "C3172"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3172"
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3172
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'module\_name': 한 프로젝트에 다른 idl\_module 특성을 지정할 수 없습니다.  
  
 컴파일할 때 두 개의 파일에서 이름은 동일하지만 `dllname` 또는 `version` 매개 변수가 다른 [idl\_module](../../windows/idl-module.md) 특성이 발견되었습니다.  컴파일 당 고유한 `idl_module` 특성을 하나만 지정할 수 있습니다.  
  
 둘 이상의 소스 코드 파일에 동일한 `idl_module` 특성을 지정할 수 있습니다.  
  
 예를 들어 다음과 같은 `idl_module` 특성이 발견되는 경우 이 오류가 발생합니다. 첫 번째 코드 파일:  
  
```  
// C3172.cpp  
[module(name="MyMod")];  
[ idl_module(name="x", dllname="file.dll", version="1.1") ];  
int main() {}  
```  
  
 두 번째 코드 파일:  
  
```  
// C3172b.cpp  
// compile with: C3172.cpp  
// C3172 expected  
[ idl_module(name="x", dllname="file.dll", version="1.0") ];  
```  
  
 여기서, 버전 값이 서로 다르다는 점에 유의하십시오.