---
title: "컴파일러 오류 C3121 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3121
dev_langs:
- C++
helpviewer_keywords:
- C3121
ms.assetid: 1d3c7be4-d42d-4def-8d53-182c0c5cc237
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 56e97505119f16cf81fdc216527af39eaa837dba
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3121"></a>컴파일러 오류 C3121
'class_name' 클래스에 대 한 GUID를 변경할 수 없습니다.  
  
 클래스 ID를 변경 하려고 했습니다. [__declspec (uuid)](../../cpp/uuid-cpp.md)합니다.  
  
 예를 들어 다음 코드에서는 C3121를 생성합니다.  
  
```  
// C3121.cpp  
[emitidl];  
[module(name="MyLibrary")];  
  
[coclass, uuid="00000000-0000-0000-0000-111111111111"]  
class __declspec(uuid("00000000-0000-0000-0000-111111111112")) A   // C3121  
{  
};  
int main()  
{  
}  
```
