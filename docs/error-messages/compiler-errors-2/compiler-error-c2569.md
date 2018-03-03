---
title: "컴파일러 오류 C2569 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2569
dev_langs:
- C++
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e99e8192d12ed37cf6ec258df8c14f61003a750d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2569"></a>컴파일러 오류 C2569
'EnumOrUnion': 열거형/공용 구조체를 기본 클래스로 사용할 수 없습니다  
  
 형식으로 지정 된 공용 구조체 또는 열거형에서 파생 되어야 하는 경우 클래스 또는 구조체를 공용 구조체 또는 열거형을 변경 합니다.  
  
 다음 샘플에서는 C2569 오류가 생성 됩니다.  
  
```  
// C2569.cpp  
// compile with: /c  
union ubase {};  
class cHasPubUBase : public ubase {};   // C2569  
// OK  
struct sbase {};  
class cHasPubUBase : public sbase {};  
```