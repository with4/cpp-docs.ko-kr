---
title: 컴파일러 경고 (수준 1) C4743 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4743
dev_langs:
- C++
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84b4d5f3aa465257d7efcf9f95584612214165b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282667"
---
# <a name="compiler-warning-level-1-c4743"></a>컴파일러 경고(수준 1) C4743
'*형식*'다른 크기의 '*file1*'및'*file2*': *번호* 및 *번호* 바이트  
  
 두 개의 파일에 정의 된 또는 참조는 외부 변수 범위는 해당 파일의 다양 한 종류와 컴파일러에서 확인 하는 변수의 크기 *file1* 변수의 크기와 다른 *file2*.  
  
 됩니다. 중요 한 경우 c + +에 대 한이 경고가 발생할 수 있습니다. 이러한 선언에는 가상 함수를 포함 하 고 선언 된 동일 하지 않은 경우 서로 다른 두 파일에 같은 이름의 동일한 형식으로 선언 하면 컴파일러가 C4744 가상 함수 테이블에 대 한 경고를 내보낼 수 있습니다. 경고에는 동일한 형식에 대 한 두 개의 서로 다른 크기의 가상 함수 테이블은 링커를 실행 파일로 통합 되도록 중 하나를 선택 해야 하기 때문에 발생 합니다.  잘못 된 가상 함수를 호출 하 여 프로그램에서 발생할 수 있습니다이 불가능 합니다.  
  
 이 경고를 해결 하려면 같은 형식 정의 사용 하거나 다른 형식 또는 변수 이름을 사용 합니다.  
  
## <a name="example"></a>예제  
 이 샘플 유형에 대 한 하나의 정의 포함합니다.  
  
```  
// C4743a.cpp  
// compile with: /c  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
};  
  
void C::f1(void) {}  
void C::f2(void) {}  
void C::f3(void) {}  
C q;  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4743 오류가 발생 합니다.  
  
```  
// C4743b.cpp  
// compile with: C4743a.cpp /W1 /GL /O2  
// C4743 expected  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
    virtual void f4(void);  
    virtual void f5(void);  
};  
  
void C::f4(void) {}  
void C::f5(void) {}  
C x;  
  
int main() {}   
```