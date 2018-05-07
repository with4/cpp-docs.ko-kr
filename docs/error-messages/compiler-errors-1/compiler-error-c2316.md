---
title: 컴파일러 오류 C2316 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2316
dev_langs:
- C++
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 895db6535299a077bc32b6485a360ae450e6c87e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2316"></a>컴파일러 오류 C2316

> '*예외*': 복사 생성자 및/또는 소멸자에 액세스할 수 없는 대로 낼 수 없습니다  
  
값별 또는 참조별 예외가 catch되었지만 복사 생성자 및/또는 대입 연산자에 액세스할 수 없습니다.  
  
이 코드 버전의 Visual Studio 2003 이전 Visual c + +에서 수락한 하지만 이제 오류가 발생 합니다.  
  
Visual Studio 2015에서 규칙에 따라 변경의 MFC 예외에서 파생 된 잘못 된 catch 문에 적용이 오류 `CException`합니다. 때문에 `CException` 클래스는 상속 된 전용 복사 생성자가 파생 하 고 복사할 수 없는 또한 값별로 찾아낼 수 없습니다 것을 의미 하는 값으로 전달할 수 없습니다. 이전에 어 졌으 런타임 시 예외를 확인할 수 없는 값으로 MFC 예외를 발생 하는 문을 catch 하지만 이제 컴파일러 정확 하 게 식별 및이 문제를 C2316 오류를 보고 합니다. 이 문제를 해결 하려면 코드에 적합 하지 않은 경우 예외를 catch MFC 참조로 대신 있지만 사용자 고유의 예외 처리기를 작성 하지 않고 MFC TRY/CATCH 매크로 사용 하는 것이 좋습니다.   
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2316을 생성합니다.  
  
```  
// C2316.cpp  
// compile with: /EHsc  
#include <stdio.h>  
  
extern "C" int printf_s(const char*, ...);  
  
struct B   
{  
public:  
    B() {}  
    // Delete the following line to resolve.  
private:  
    // copy constructor  
    B(const B&)   
    {  
    }  
};  
  
void f(const B&)   
{  
}  
  
int main()   
{  
    try   
    {  
        B aB;  
        f(aB);  
    }  
    catch (B b) {   // C2316  
        printf_s("Caught an exception!\n");     
    }  
}  
```