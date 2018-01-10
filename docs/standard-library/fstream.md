---
title: "&lt;fstream&gt; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <fstream>
dev_langs: C++
helpviewer_keywords: fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d41719c7ff7ce2d7a906395ed65b891e2583bac8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;
외부 파일에 저장된 시퀀스에 대한 Iostreams 작업을 지원하는 여러 클래스를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <fstream>  
  
```  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|`char` 템플릿 매개 변수에서 특수화된 `basic_filebuf` 형식입니다.|  
|[fstream](../standard-library/fstream-typedefs.md#fstream)|`char` 템플릿 매개 변수에서 특수화된 `basic_fstream` 형식입니다.|  
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|`char` 템플릿 매개 변수에서 특수화된 `basic_ifstream` 형식입니다.|  
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|`char` 템플릿 매개 변수에서 특수화된 `basic_ofstream` 형식입니다.|  
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|`wchar_t` 템플릿 매개 변수에서 특수화된 `basic_fstream` 형식입니다.|  
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|`wchar_t` 템플릿 매개 변수에서 특수화된 `basic_ifstream` 형식입니다.|  
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|`wchar_t` 템플릿 매개 변수에서 특수화된 `basic_ofstream` 형식입니다.|  
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|`wchar_t` 템플릿 매개 변수에서 특수화된 `basic_filebuf` 형식입니다.|  
  
### <a name="classes"></a>클래스  
  
|||  
|-|-|  
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|템플릿 클래스는 외부 파일에 저장된 요소의 시퀀스에서 나가고 들어오는 **Elem** 형식 요소의 전송을 제어하는 스트림 버퍼에 대해 설명하며, 해당 문자 특성은 **Tr** 클래스로 결정됩니다.|  
|[basic_fstream](../standard-library/basic-fstream-class.md)|이 템플릿 클래스는 문자 특성이 **Tr** 클래스에 의해 결정되는 **Elem** 형식의 요소가 있는 [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> 클래스의 스트림 버퍼를 사용한 요소 및 인코드된 개체의 삽입 및 추출을 제어하는 개체를 설명합니다.|  
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|이 템플릿 클래스는 문자 특성이 **Tr** 클래스에 의해 결정되는 **Elem** 형식의 요소가 있는 [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> 클래스의 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어하는 개체를 설명합니다.|  
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|이 템플릿 클래스는 문자 특성이 **Tr** 클래스에 의해 결정되는 **Elem** 형식의 요소가 있는 [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> 클래스의 스트림 버퍼에 요소 및 인코드된 개체의 삽입을 제어하는 개체를 설명합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)



