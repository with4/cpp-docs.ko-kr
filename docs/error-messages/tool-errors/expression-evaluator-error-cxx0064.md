---
title: "식 계산기 오류 CXX0064 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0064
dev_langs: C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2edeb05e39c6d2e70cb2c9dde562a89e85921301
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0064"></a>식 계산기 오류 CXX0064
바인딩된 가상 멤버 함수에 중단점을 설정할 수 없습니다.  
  
 와 같은 개체에 대 한 포인터를 통해 가상 멤버 함수에 중단점 설정 되었습니다.  
  
```  
pClass->vfunc( int );  
```  
  
 와 같은 클래스를 입력 하 여 가상 함수에 중단점을 설정할 수 있습니다.  
  
```  
Class::vfunc( int );  
```  
  
 이 오류는 can0064와 동일 합니다.