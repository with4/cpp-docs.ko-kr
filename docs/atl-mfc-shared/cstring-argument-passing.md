---
title: "CString 인수 전달 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- strings [C++], as function input/output
- argument passing [C++]
- arguments [C++], passing
- functions [C++], strings as input/output
- argument passing [C++], C strings
- passing arguments, C strings
- CString objects, passing arguments
- string arguments
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d33c8cc46ada41f851c90aaae0cabfadb1466d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cstring-argument-passing"></a>CString 인수 전달
이 문서에서는 전달 하는 방법을 설명 [CString](../atl-mfc-shared/reference/cstringt-class.md) 함수 및 반환 하는 방법에 대 한 개체 `CString` 함수에서 개체입니다.  
  
##  <a name="_core_cstring_argument.2d.passing_conventions"></a>CString 인수 전달 규칙  
 클래스 인터페이스를 정의 하는 경우에 멤버 함수에 대 한 인수 전달 규칙을 결정 해야 합니다. 전달 및 반환에 대 한 몇 가지 표준 규칙은 `CString` 개체입니다. 에 설명 된 규칙을 따르는 경우 [함수 입력으로 문자열](#_core_strings_as_function_inputs) 및 [함수는 출력으로 문자열](#_core_strings_as_function_outputs)을 효율적이 고 올바른 코드를 갖습니다.  
  
##  <a name="_core_strings_as_function_inputs"></a>함수가 입력으로 문자열  
 사용 하는 가장 효율적이 고 안전한 방법은 `CString` 호출된 되는 함수에 개체를 전달 하는 한 `CString` 함수에는 개체입니다. 이름이 `CString` 개체는 null 종결자를가 하는 C 스타일 문자열로 문자열을 내부적으로 저장 하지는 않습니다. 대신,는 `CString` 개체 깊게 추적에는 문자 수를 보관 합니다. 필요 `CString` 제공는 `LPCTSTR` null로 끝나는 문자열에 대 한 포인터는 적은 양의 작업을 지속적으로 작업을 수행 하려면 코드에 중요할 수 있습니다. 결과 변경 때문에 임시는 `CString` 의 이전 복사본을 무효화 하는 콘텐츠는 `LPCTSTR` 포인터입니다.  
  
 않습니다 좋을 C 스타일 문자열을 제공 하는 경우도 있습니다. 예를 들어,이 경우 호출된 된 함수는 C로 작성 된 개체를 지원 하지 않는 있을 수 있습니다. 이 경우 강제는 `CString` 매개 변수를 `LPCTSTR`, 함수는 C 스타일 null로 끝나는 문자열을 받게 됩니다. 또한 다른 방향 이동 하 고 만들 수 있습니다는 `CString` 사용 하 여 개체는 `CString` C 스타일 문자열 매개 변수를 허용 하는 생성자입니다.  
  
 문자열 내용이 함수에 의해 변경 될 경우는 nonconstant으로 매개 변수를 선언 `CString` 참조 (**CString &**).  
  
##  <a name="_core_strings_as_function_outputs"></a>함수는 출력으로 문자열  
 일반적으로 반환할 수 있습니다 `CString` 때문에 함수에서 개체를 `CString` 개체는 기본 형식과 마찬가지로 값 의미 체계를 준수 합니다. 읽기 전용 문자열을 반환 하려면 상수를 사용 하 여 `CString` 참조 (**const CString &**). 다음 예제에서는 `CString` 매개 변수 및 반환 형식:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/cpp/cstring-argument-passing_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

