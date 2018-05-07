---
title: 컴파일러 오류 C2030 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2030
dev_langs:
- C++
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ceccc1088e32382167e7e6400360b30de07fde1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2030"></a>컴파일러 오류 C2030
'protected private' 접근성을 가진 소멸자는 'sealed'로 선언된 클래스의 멤버일 수 없습니다.  
  
 `sealed`로 선언된 Windows 런타임 클래스에는 protected private 소멸자가 없을 수 있습니다. sealed 형식에서는 public virtual 및 private non-virtual 소멸자만 허용됩니다. 자세한 내용은 참조 [Ref 클래스 및 구조체](../../cppcx/ref-classes-and-structs-c-cx.md)합니다.  
  
 이 오류를 해결하려면 소멸자의 접근성을 변경합니다.