---
title: 컴파일러 경고 (수준 2) C4275 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4275
dev_langs:
- C++
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5d2a3cd7c4b937f8bee1b8f8e37e0619cc224ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4275"></a>컴파일러 경고(수준 2) C4275
비-DLL 인터페이스 classkey 'identifier' 기준으로 사용 DLL 인터페이스 classkey 'identifier'  
  
 내보낸된 클래스 내보내지 않은 클래스에서 파생 되었습니다.  
  
 사용 하는 클래스를 내보낼 때 데이터 손상 가능성을 최소화 하려면 [__declspec (dllexport)](../../cpp/dllexport-dllimport.md), 되어 있는지 확인 합니다.  
  
-   모든 정적 데이터 DLL에서 내보낸 함수를 통해 액세스 됩니다.  
  
-   클래스의 메서드가 없는 인라인된 정적 데이터를 수정할 수 있습니다.  
  
-   클래스의 인라인된 메서드가 없는 CRT 함수를 사용 하거나 다른 라이브러리 함수는 정적 데이터를 사용 합니다.  
  
-   인라인된 클래스 함수가 없습니다 정적 데이터를 액세스 예를 들어, where, CRT 함수 또는 다른 라이브러리 함수에 사용 합니다.  
  
-   클래스의 메서드가 없는 (에 관계 없이 인라이닝) 인스턴스화 EXE 및 DLL에는 정적 데이터 차이점이 형식을 사용할 수 있습니다.  
  
 함수 및 가상 함수를 사용 하 여 클래스를 정의 하는 DLL 인스턴스화하기 위해 호출할 수를 정의 하 고 유형의 개체를 삭제 하면 클래스를 내보내지 방지할 수 있습니다.  그런 다음 가상 함수 형식에만 호출할 수 있습니다.  
  
 서식 파일을 내보내는 방법에 대 한 자세한 내용은 참조 하십시오. [ http://support.microsoft.com/default.aspx?scid=KB; EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958)합니다.  
  
 디버그 릴리스를 컴파일하면 c + + 표준 라이브러리의 형식에서 파생 하는 경우 Visual c + +에서 c 4275를 무시할 수 있습니다 (**/MTd**) 하 고 _Container_base 컴파일러 오류 메시지는 위치입니다.  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```