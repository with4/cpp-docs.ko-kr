---
title: "컴파일러 오류 C3172 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3172
dev_langs:
- C++
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: a53e7bc0b8543813e5745773f6a7548eb9a83442
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-error-c3172"></a>컴파일러 오류 C3172
'모듈': 한 프로젝트에 다른 idl_module 특성을 지정할 수 없습니다  
  
 [idl_module](../../windows/idl-module.md) 특성과 동일 하지만 서로 다른 이름을 `dllname` 또는 `version` 컴파일에 파일의 두 매개 변수가 발견 되었습니다. 고유한 하나만 `idl_module` 컴파일마다 특성을 지정할 수 있습니다.  
  
 동일한 `idl_module` 둘 이상의 소스 코드 파일에서 특성을 지정할 수 있습니다.  
  
 예를 들어 경우 다음 `idl_module` 특성이 발견 되었습니다.  
  
```  
// C3172.cpp  
[module(name="MyMod")];  
[ idl_module(name="x", dllname="file.dll", version="1.1") ];  
int main() {}  
```  
  
 그리고  
  
```  
// C3172b.cpp  
// compile with: C3172.cpp  
// C3172 expected  
[ idl_module(name="x", dllname="file.dll", version="1.0") ];  
```  
  
 다르다는 C3172 (버전 값이 서로 참고).
