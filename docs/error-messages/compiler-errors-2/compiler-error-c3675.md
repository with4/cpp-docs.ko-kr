---
title: "컴파일러 오류 C3675 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3675
dev_langs: C++
helpviewer_keywords: C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6545b7cfa8232ba8b48df104ce848eb34c0e108c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3675"></a>컴파일러 오류 C3675
'function': 'property' 정의 되었기 때문에 예약 되어  
  
 Get 및 set 접근자 메서드를 권한과 컴파일러 생성 간단한 속성을 선언 하는 경우 이름이 프로그램의 범위에 표시 되어 있습니다.  컴파일러에서 생성 한 이름이 get_ 및 set_를 속성 이름 앞에 추가 하 여 구성 됩니다.  따라서 컴파일러에서 생성 된 접근자와 같은 이름 사용 하 여 함수를 선언할 수 없습니다.  
  
 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md) 를 참조하세요.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3675 오류가 발생 합니다.  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```