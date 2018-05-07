---
title: 컴파일러 오류 C3451 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3451
dev_langs:
- C++
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a8aa09f0eb38364179be1608c3f230fe8059509
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3451"></a>컴파일러 오류 C3451
'attribute': 관리 되지 않는 특성을 't y'를 적용할 수 없습니다  
  
 C + + 특성 CLR 형식에 적용할 수 없습니다. 참조 [c + + 특성 참조](../../windows/cpp-attributes-reference.md) 자세한 정보에 대 한 합니다.  
  
 자세한 내용은 [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)을 참조하세요.  
  
 이 오류는 Visual c + + 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 없습니다:는 [uuid](../../windows/uuid-cpp-attributes.md) 특성은 CLR 프로그래밍을 사용 하 여 사용자 정의 특성에 더 이상 사용할 수 없습니다. 대신 <xref:System.Runtime.InteropServices.GuidAttribute>를 사용하세요.  
  
## <a name="example"></a>예제  
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