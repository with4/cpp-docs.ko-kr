---
title: "컴파일러 오류 C3172 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3172
dev_langs:
- C++
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3390c0f1f566e28bc6a000b2ff570c781c93bc98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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