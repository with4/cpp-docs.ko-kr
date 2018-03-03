---
title: "컴파일러 오류 C3451 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3451
dev_langs:
- C++
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cb68c546a9064801c68844039b7de077d5ee7c17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3451"></a>컴파일러 오류 C3451
'attribute': 관리 되지 않는 특성을 't y'를 적용할 수 없습니다  
  
 C + + 특성 CLR 형식에 적용할 수 없습니다. 참조 [c + + 특성 참조](../../windows/cpp-attributes-reference.md) 자세한 정보에 대 한 합니다.  
  
 자세한 내용은 [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)을 참조하세요.  
  
 이 오류는 Visual c + + 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 없습니다:는 [uuid](../../windows/uuid-cpp-attributes.md) 특성은 CLR 프로그래밍을 사용 하 여 사용자 정의 특성에 더 이상 사용할 수 없습니다. 대신 <xref:System.Runtime.InteropServices.GuidAttribute>를 사용하세요.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3451 오류가 발생 합니다.  
  
```  
// C3451.cpp  
// compile with: /clr /c  
using namespace System;  
[ attribute(AttributeTargets::All) ]  
public ref struct MyAttr {};  
  
[ MyAttr, helpstring("test") ]   // C3451  
// try the following line instead  
// [ MyAttr ]  
public ref struct ABC {};  
```