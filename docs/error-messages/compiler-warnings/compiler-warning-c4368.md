---
title: 컴파일러 경고 C4368 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4368
dev_langs:
- C++
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3a7e53c979a3b13bde205a4546c486061a17110
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4368"></a>컴파일러 경고 C4368
'member' 관리 되는 'type'의 멤버로 정의할 수 없습니다: 혼합된 형식은 지원 되지 않습니다  
  
 CLR 형식에 네이티브 데이터 멤버를 포함할 수 없습니다.  
  
 하지만 네이티브 형식에 대한 포인터를 선언하고, 관리 클래스의 생성자 및 소멸자와 종료자에서 해당 수명을 제어할 수 있습니다. 자세한 내용은 참조 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)합니다.  
  
 항상이 경고는 오류로 발생 됩니다. 사용 하 여는 [경고](../../preprocessor/warning.md) pragma를 C4368를 사용 하지 않도록 설정 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4368 오류가 발생 합니다.  
  
```  
// C4368.cpp  
// compile with: /clr /c  
struct N {};  
ref struct O {};  
ref struct R {  
    R() : m_p( new N ) {}  
    ~R() { delete m_p; }  
  
   property N prop;   // C4368  
   int i[10];   // C4368  
  
   property O ^ prop2;   // OK  
   N * m_p;   // OK  
};  
```