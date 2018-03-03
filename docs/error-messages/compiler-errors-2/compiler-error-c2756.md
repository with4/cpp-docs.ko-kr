---
title: "컴파일러 오류 c 2756 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2756
dev_langs:
- C++
helpviewer_keywords:
- C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 55d129583f56ea60a7e9dccdcd7006a73a3733d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2756"></a>컴파일러 오류 c 2756
'template type' : 부분 특수화에는 기본 템플릿 인수를 사용할 수 없습니다.  
  
 부분 특수화에 대한 템플릿에는 기본 인수가 포함될 수 없습니다.  
  
 다음 샘플에서는 C2756을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2756.cpp  
template <class T>  
struct S {};  
  
template <class T=int>  
// try the following line instead  
// template <class T>  
struct S<T*> {};   // C2756  
```