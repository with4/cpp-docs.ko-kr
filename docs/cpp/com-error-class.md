---
title: "_com_error 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 53defbe6c686630791317fa20aca48414144eb91
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="comerror-class"></a>_com_error 클래스
**Microsoft 전용**  
  
 A `_com_error` 개체 형식 라이브러리에서 생성 된 헤더 파일의 오류 처리 래퍼 함수에서 또는 COM 지원 클래스 중 하나를 통해 검색 되는 예외 상태를 나타냅니다. `_com_error` 클래스 캡슐화는 `HRESULT` 오류 코드와 모든 관련 `IErrorInfo Interface` 개체입니다.  
  
### <a name="construction"></a>생성  
  
|||  
|-|-|  
|[_com_error](../cpp/com-error-com-error.md)|`_com_error` 개체를 생성합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator =](../cpp/com-error-operator-equal.md)|기존 `_com_error` 개체를 다른 개체에 할당합니다.|  
  
### <a name="extractor-functions"></a>기능 추출기  
  
|||  
|-|-|  
|[오류](../cpp/com-error-error.md)|생성자에 전달된 `HRESULT`를 검색합니다.|  
|[ErrorInfo](../cpp/com-error-errorinfo.md)|검색 된 `IErrorInfo` 개체 생성자에 전달 합니다.|  
|[WCode](../cpp/com-error-wcode.md)|캡슐화된 `HRESULT`에 매핑되는 16비트 오류 코드를 검색합니다.|  
  
### <a name="ierrorinfo-functions"></a>IErrorInfo 함수  
  
|||  
|-|-|  
|[설명](../cpp/com-error-description.md)|호출 `IErrorInfo::GetDescription` 함수입니다.|  
|[HelpContext](../cpp/com-error-helpcontext.md)|호출 `IErrorInfo::GetHelpContext` 함수입니다.|  
|[HelpFile](../cpp/com-error-helpfile.md)|호출 `IErrorInfo::GetHelpFile` 함수|  
|[Source](../cpp/com-error-source.md)|호출 `IErrorInfo::GetSource` 함수입니다.|  
|[GUID](../cpp/com-error-guid.md)|호출 `IErrorInfo::GetGUID` 함수입니다.|  
  
### <a name="format-message-extractor"></a>형식 메시지 추출기  
  
|||  
|-|-|  
|[ErrorMessage](../cpp/com-error-errormessage.md)|에 저장 된 HRESULT에 대 한 문자열 메시지를 검색 하는 `_com_error` 개체입니다.|  
  
### <a name="exepinfowcode-to-hresult-mappers"></a>HRESULT 매퍼를 ExepInfo.wCode  
  
|||  
|-|-|  
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|32 비트 매핑합니다 `HRESULT` 에 16 비트 `wCode`합니다.|  
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|16비트 `wCode`를 32비트 `HRESULT`로 매핑합니다.|  
  
**Microsoft 전용 종료**  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<comdef.h >  
  
 `Lib:`에서는 comsuppw.lib 또는 comsuppwd.lib (참조 [/zc: wchar_t (wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 자세한 내용은)  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)   
 [IErrorInfo 인터페이스](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)