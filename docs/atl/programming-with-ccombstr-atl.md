---
title: "CComBSTR을 사용한 프로그래밍(ATL) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComBSTR 클래스, 프로그래밍"
  - "Unicode, CComBSTR 사용[ATL]"
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComBSTR을 사용한 프로그래밍(ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL 클래스  [CComBSTR](../atl/reference/ccombstr-class.md) 는 래퍼를 제공 된 `BSTR` 데이터 형식.  하지만 `CComBSTR` 는 유용한 도구입니다 주의 필요로 하는 여러 가지 상황.  
  
-   [변환 문제](#programmingwithccombstr_conversionissues)  
  
-   [범위 문제](#programmingwithccombstr_scopeissues)  
  
-   [CComBSTR 개체를 명시적으로 해제](#programmingwithccombstr_explicitlyfreeing)  
  
-   [루프에서 CComBSTR 개체 사용](#programmingwithccombstr_usingloops)  
  
-   [메모리 누수 문제](#programmingwithccombstr_memoryleaks)  
  
##  <a name="programmingwithccombstr_conversionissues"></a> 변환 문제  
 하지만 몇 가지 `CComBSTR` 메서드는 ANSI 문자열 인수 유니코드로 변환 자동으로 됩니다, 메서드는 항상 유니코드 형식 문자열을 반환 합니다.  출력 문자열을 ANSI로 다시 변환 하려면 ATL 변환 클래스를 사용 합니다.  ATL 변환 클래스에 대 한 자세한 내용은  [ATL 및 MFC 문자열 변환 매크로](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
### 예제  
 [!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/CPP/programming-with-ccombstr-atl_1.cpp)]  
  
 수정 하는 리터럴 문자열을 사용 하는 경우는 `CComBSTR` 개체, 와이드 문자 문자열을 사용 합니다.  이 불필요 한 변환을 줄일 수 있습니다.  
  
### 예제  
 [!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/CPP/programming-with-ccombstr-atl_2.cpp)]  
  
##  <a name="programmingwithccombstr_scopeissues"></a> 범위 문제  
 제대로 작동 클래스에 있는 `CComBSTR` 범위를 벗어날 때 해당 리소스를 해제 합니다.  함수 포인터를 반환 하는 경우는 `CComBSTR` 문자열을이 발생할 수 있습니다 문제를 이미 해제 된 메모리 포인터를 참조 하는.  이러한 경우에 사용 하는  **복사** 메서드를 아래와 같이 합니다.  
  
### 예제  
 [!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/CPP/programming-with-ccombstr-atl_3.cpp)]  
  
##  <a name="programmingwithccombstr_explicitlyfreeing"></a> CComBSTR 개체를 명시적으로 해제  
 포함 된 문자열을 명시적으로 해제할 수는 `CComBSTR` 범위 개체를 이동 하기 전에 개체.  문자열을 해제 하는 경우는 `CComBSTR` 개체가 잘못 되었습니다.  
  
### 예제  
 [!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/CPP/programming-with-ccombstr-atl_4.cpp)]  
  
##  <a name="programmingwithccombstr_usingloops"></a> 루프에서 CComBSTR 개체 사용  
 으로 `CComBSTR` 클래스와 같은 특정 작업을 수행 하는 버퍼를 할당의 `+=` 연산자 또는  **추가** 메서드는 권장 되지 않습니다 반복 되는 루프 내의 문자열 조작을 수행 하는 것입니다.  이러한 상황에서 `CStringT` 더 나은 성능을 제공 합니다.  
  
### 예제  
 [!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/CPP/programming-with-ccombstr-atl_5.cpp)]  
  
##  <a name="programmingwithccombstr_memoryleaks"></a> 메모리 누수 문제  
 전달 주소는 초기화의 `CComBSTR` 서 함수는  **\[out\]** 매개 변수는 메모리 누수가 발생 합니다.  
  
 아래 예제는 문자열 할당 된 문자열을 저장할 수 `"Initialized"` 때 누수 함수 `MyGoodFunction` 문자열을 바꿉니다.  
  
 [!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/CPP/programming-with-ccombstr-atl_6.cpp)]  
  
 메모리 누수를 방지 하려면 호출을  **빈** 메서드를 기존 `CComBSTR` 개체의 주소를 전달 하기 전에  **\[out\]** 매개 변수.  
  
 참고 동일한 코드는 함수 매개 변수 이면 누수가 칠해지지 않는  **\[in, out\]**.  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)   
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)   
 [wstring](../Topic/wstring.md)   
 [String Conversion Macros](../atl/reference/string-conversion-macros.md)