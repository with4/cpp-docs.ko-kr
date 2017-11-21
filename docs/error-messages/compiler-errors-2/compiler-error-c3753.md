---
title: "컴파일러 오류 C3753 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3753
dev_langs: C++
helpviewer_keywords: C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 93150c018159a649e772406a5a9a96836b87da8a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3753"></a>컴파일러 오류 C3753
일반 속성을 사용할 수 없습니다.  
  
 제네릭 매개 변수 목록은 관리 되는 클래스, 구조체 또는 함수에만 사용할 수 있습니다.  
  
 자세한 내용은 참조 [제네릭](../../windows/generics-cpp-component-extensions.md) 및 [속성](../../windows/property-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3753 오류가 발생 합니다.  
  
```  
// C3753.cpp  
// compile with: /clr /c  
ref struct A {  
   generic <typename T>  
   property int i;   // C3753 error  
};  
```