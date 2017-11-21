---
title: "컴파일러 오류 C2364 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2364
dev_langs: C++
helpviewer_keywords: C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d7c5042d4b5984a87b52cefafd1f591ec662ab48
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2364"></a>컴파일러 오류 C2364
'type': 사용자 지정 특성에 대 한 형식이 잘못 되었습니다.  
  
 사용자 지정 특성에 대 한 명명 된 인수는 컴파일 시간 상수 제한 합니다. (Int, char 등) 예를 들어 정수 계열 형식 system:: type ^, 및 system:: object ^ 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2364 오류가 발생 합니다.  
  
```  
// c2364.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute(AttributeTargets::All)]  
public ref struct ABC {  
public:  
   // Delete the following line to resolve.  
   ABC( Enum^ ) {}   // C2364  
   ABC( int ) {}   // OK  
};  
```