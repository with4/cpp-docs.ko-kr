---
title: "컴파일러 오류 C3215 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3215
dev_langs:
- C++
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf9e1f0b726f8b77a8943a5c6495b67f9d3e252c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3215"></a>컴파일러 오류 C3215
'type1': 제네릭 형식 매개 변수가 이미 'type2'의 제약을 받습니다.  
  
 제약 조건을 두 번 이상 지정했습니다.  
  
 제네릭에 대한 자세한 내용은 [Generics](../../windows/generics-cpp-component-extensions.md)을 참조하세요.  
  
 다음 샘플에서는 C3215를 생성합니다.  
  
```  
// C3215.cpp  
// compile with: /clr  
interface struct A {};  
  
generic <class T>  
where T : A,A  
ref class C {};   // C3215  
```  
  
 해결 방법:  
  
```  
// C3215b.cpp  
// compile with: /clr /c  
interface struct A {};  
  
generic <class T>  
where T : A  
ref class C {};  
```