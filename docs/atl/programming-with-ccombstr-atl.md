---
title: "CComBSTR (ATL)을 사용한 프로그래밍 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f8f496dd73c2d15f8f78ddbdc205f31a8520c674
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="programming-with-ccombstr-atl"></a>CComBSTR을 사용한 프로그래밍(ATL)
ATL 클래스 [CComBSTR](../atl/reference/ccombstr-class.md) 에 래퍼를 제공는 `BSTR` 데이터 형식입니다. 동안 `CComBSTR` 는 유용한 도구와 같은 경우 유의 해야 합니다.  
  
-   [변환 문제](#programmingwithccombstr_conversionissues)  
  
-   [범위 문제](#programmingwithccombstr_scopeissues)  
  
-   [CComBSTR 개체를 명시적으로 해제](#programmingwithccombstr_explicitlyfreeing)  
  
-   [루프에서 CComBSTR 개체 사용](#programmingwithccombstr_usingloops)  
  
-   [메모리 누수 문제](#programmingwithccombstr_memoryleaks)  
  
##  <a name="programmingwithccombstr_conversionissues"></a>변환 문제  
 하지만 여러 가지 `CComBSTR` 메서드에서 자동으로 변환 ANSI 문자열 인수를 유니코드로, 메서드는 항상 유니코드 형식 문자열을 반환 합니다. 출력 문자열 다시 ANSI로 변환할 ATL 변환 클래스를 사용 합니다. ATL 변환 클래스에 대 한 자세한 내용은 참조 하십시오. [ATL 및 MFC 문자열 변환 매크로](reference/string-conversion-macros.md)합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]  
  
 문자열 리터럴을 사용 하 여 수정 하는 경우는 `CComBSTR` 개체, 와이드 문자 문자열을 사용 합니다. 이렇게 하면 불필요 한 변환을 줄어듭니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]  
  
##  <a name="programmingwithccombstr_scopeissues"></a>범위 문제  
 제대로 작동 하는 클래스와 마찬가지로 `CComBSTR` 범위를 벗어나면 해당 리소스를 해제 합니다. 함수에 대 한 포인터를 반환 하는 경우는 `CComBSTR` 문자열 포인터는 이미 해제 된 메모리를 참조 하는 대로 문제를 발생할 수 있습니다. 이 경우에 사용 된 **복사** 메서드를 다음과 같이 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]  
  
##  <a name="programmingwithccombstr_explicitlyfreeing"></a>CComBSTR 개체를 명시적으로 해제  
 에 포함 된 문자열을 명시적으로 해제 수는 `CComBSTR` 범위를 벗어나기 전에 개체입니다. 문자열이 해제 됩니다 하는 경우는 `CComBSTR` 개체가 잘못 되었습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]  
  
##  <a name="programmingwithccombstr_usingloops"></a>루프에서 CComBSTR 개체 사용  
 로 `CComBSTR` 와 같은 특정 작업을 수행 하는 버퍼를 할당 하는 클래스는 `+=` 연산자 또는 **Append** 메서드를 권장 되지 않습니다 루프 내의 문자열 조작 수행 하는 합니다. 이러한 상황에서는 `CStringT` 더 나은 성능을 제공 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]  
  
##  <a name="programmingwithccombstr_memoryleaks"></a>메모리 누수 문제  
 초기화 된의 주소를 전달 `CComBSTR` 서 함수에는 **[out]** 매개 변수에서 메모리 누수가 발생 합니다.  
  
 아래 예제에서는 문자열에 할당할 때 문자열을 저장할 `"Initialized"` 가 유출 함수 `MyGoodFunction` 문자열을 대체 합니다.  
  
 [!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]  
  
 호출 하 여 누수를 방지 하려면는 **빈** 메서드를 기존 `CComBSTR` 개체 주소를 전달 하기 전에 **[out]** 매개 변수입니다.  
  
 동일한 코드는 함수의 매개 변수가 경우 누수가 발생 하지 것에 유의 **[에, out]**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)   
 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)   
 [wstring](../standard-library/basic-string-class.md)   
 [문자열 변환 매크로](../atl/reference/string-conversion-macros.md)

