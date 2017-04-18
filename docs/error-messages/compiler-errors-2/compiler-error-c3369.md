---
title: "컴파일러 오류 C3369 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3369
dev_langs:
- C++
helpviewer_keywords:
- C3369
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: a8e195a4dba4964d0ed487ad4ebd189190467155
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3369"></a>컴파일러 오류 C3369
'module name': idl_module이 이미 정의되었습니다.  
  
 [idl_module](../../windows/idl-module.md) 정의 하는 경우 DLL 사용 프로그램에서 한 번 발생만 수 있습니다.  
  
 다음 샘플에서는 C3369를 생성합니다.  
  
```  
// C3369.cpp  
// compile with: /c  
[idl_module(name="name1", dllname="x.dll")]; // C3369  
[idl_module(name="name1", dllname="x.dll")];  
```
