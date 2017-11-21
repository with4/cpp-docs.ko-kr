---
title: "컴파일러 오류 C2030 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2030
dev_langs: C++
helpviewer_keywords: C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a2efd868160e3ec7e5bf356603cc821a0b07f149
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2030"></a>컴파일러 오류 C2030
'protected private' 접근성을 가진 소멸자는 'sealed'로 선언된 클래스의 멤버일 수 없습니다.  
  
 `sealed`로 선언된 Windows 런타임 클래스에는 protected private 소멸자가 없을 수 있습니다. sealed 형식에서는 public virtual 및 private non-virtual 소멸자만 허용됩니다. 자세한 내용은 참조 [Ref 클래스 및 구조체](../../cppcx/ref-classes-and-structs-c-cx.md)합니다.  
  
 이 오류를 해결하려면 소멸자의 접근성을 변경합니다.