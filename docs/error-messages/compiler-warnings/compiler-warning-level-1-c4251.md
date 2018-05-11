---
title: 컴파일러 경고 (수준 1) C4251 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4251
dev_langs:
- C++
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 366d66a38685e75e47d8921f9ebd525b334ced7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4251"></a>컴파일러 경고(수준 1) C4251
'identifier': 'type' 클래스를 'type2' 클래스의 클라이언트에서 사용할 dll 인터페이스가 없는 해야 합니다.  
  
 사용 하는 클래스를 내보낼 때 데이터 손상 가능성을 최소화 하려면 [__declspec (dllexport)](../../cpp/dllexport-dllimport.md), 되어 있는지 확인 합니다.  
  
-   모든 정적 데이터 DLL에서 내보낸 함수를 통해 액세스 됩니다.  
  
-   클래스의 메서드가 없는 인라인된 정적 데이터를 수정할 수 있습니다.  
  
-   클래스의 인라인된 메서드가 없는 CRT 함수를 사용 하거나 정적 데이터를 사용 하는 다른 라이브러리 함수 (참조 [잠재적 오류 CRT 개체 DLL 경계를 넘어 전달할](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) 자세한 정보에 대 한).  
  
-   클래스의 메서드가 없는 (에 관계 없이 인라이닝) 인스턴스화 EXE 및 DLL에는 정적 데이터 차이점이 형식을 사용할 수 있습니다.  
  
 함수 및 가상 함수를 사용 하 여 클래스를 정의 하는 DLL 인스턴스화하기 위해 호출할 수를 정의 하 고 유형의 개체를 삭제 하면 클래스를 내보내지 방지할 수 있습니다.  그런 다음 가상 함수 형식에만 호출할 수 있습니다.  
  
 서식 파일을 내보내는 방법에 대 한 자세한 내용은 참조 하십시오. [ http://support.microsoft.com/default.aspx?scid=KB; EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958)합니다.  
  
 디버그 릴리스를 컴파일하면 c + + 표준 라이브러리의 형식에서 파생 하는 경우에 C4251를 무시할 수 있습니다 (**/MTd**) 하 고 _Container_base 컴파일러 오류 메시지는 위치입니다.  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```