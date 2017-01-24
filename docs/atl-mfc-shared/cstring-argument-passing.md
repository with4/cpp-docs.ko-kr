---
title: "CString Argument Passing | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "argument passing [C++]"
  - "argument passing [C++], C strings"
  - "arguments [C++], 전달"
  - "CString objects, 인수 전달"
  - "함수[C++], strings as input/output"
  - "인수 전달, C strings"
  - "string arguments"
  - "문자열[C++], as function input/output"
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CString Argument Passing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 전달 하는 방법을 설명  [CString](../atl-mfc-shared/reference/cstringt-class.md) 함수 개체를 반환 하는 `CString` 함수에서 개체.  
  
##  <a name="_core_cstring_argument.2d.passing_conventions"></a> CString 인수 전달 규칙  
 클래스 인터페이스를 정의할 때는 멤버 함수에 대 한 인수 전달 규칙을 결정 해야 합니다.  전달 및 반환에 대 한 몇 가지 표준 규칙이 `CString` 개체입니다.  설명 하는 규칙을 따를 경우  [문자열 함수의 입력으로](#_core_strings_as_function_inputs) 및  [문자열 출력 함수](#_core_strings_as_function_outputs), 효율적이 고 올바른 코드를 해야 합니다.  
  
##  <a name="_core_strings_as_function_inputs"></a> 문자열 함수 입력  
 사용 하는 가장 효율적이 고 안전한 방법은 `CString` 개체에서 호출된 된 함수는 전달 하는 `CString` 함수 개체.  이름에도 불구 하 고는 `CString` 개체 하지 않습니다 저장할 문자열 내부적으로 null 종결자가 C 스타일 문자열로.  대신에 `CString` 개체는 문자 수를 주의 깊게 추적을 유지 합니다.  문제가 `CString` 제공 된 `LPCTSTR` 포인터는 null로 끝나는 문자열에는 적은 양의 코드 지속적으로 수행 하는 경우 상당히 커질 수 있습니다 작업.  결과 임시 이므로 변경의 `CString` 내용을 무효화의 이전 복사본의 `LPCTSTR` 포인터.  
  
 이 경우도 C 스타일 문자열을 제공할 수 있을까요.  예를 들어, 호출된 된 함수가 C로 작성 된 장소와 개체를 지원 하지 않는 상황이 있을 수 있습니다.  이 경우 강제 변환의 `CString` 매개 변수를 `LPCTSTR`, C 스타일의 null로 끝나는 문자열 함수를 받게 됩니다.  또한 다른 방향을 이동 하 고 만들 수 있는 `CString` 개체를 사용 하 여는 `CString` C 스타일 문자열 매개 변수를 받아들이는 생성자.  
  
 문자열 내용을 함수에서 변경 하는 경우 매개 변수는 nonconstant로 선언 `CString` 참조 \(**CString &**\).  
  
##  <a name="_core_strings_as_function_outputs"></a> 문자열 출력 함수  
 일반적으로 반환할 수 `CString` 개체에서 함수 때문에 `CString` 개체 기본 형식 처럼 값 의미 체계를 따릅니다.  읽기 전용 문자열을 반환 하는 상수를 사용 합니다. `CString` 참조 \(**const CString &**\).  다음 예제에서는 `CString` 매개 변수 및 반환 형식:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/CPP/cstring-argument-passing_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/CPP/cstring-argument-passing_2.cpp)]  
  
## 참고 항목  
 [문자열](../atl-mfc-shared/strings-atl-mfc.md)