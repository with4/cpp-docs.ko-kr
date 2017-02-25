---
title: "_com_error 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_error 클래스"
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# _com_error 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 이 `_com_error` 개체는 형식 라이브러리에서 생성 된 헤더 파일에서 오류 처리 래퍼 함수 또는 COM 지원 클래스 중 하나를 발견 하는 예외 조건을 나타냅니다.  이 `_com_error` 클래스는 `HRESULT` 오류와 연결된 `IErrorInfo Interface` 개체를 캡슐화합니다.  
  
### 생성  
  
|||  
|-|-|  
|[\_com\_error](../cpp/com-error-com-error.md)|`_com_error` 개체를 생성합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../cpp/com-error-operator-equal.md)|기존 `_com_error` 개체를 다른 개체에 할당합니다.|  
  
### 추출기 함수  
  
|||  
|-|-|  
|[오류](../cpp/com-error-error.md)|생성자에 전달된 `HRESULT`를 검색합니다.|  
|[ErrorInfo](../cpp/com-error-errorinfo.md)|생성자에 전달된 `IErrorInfo` 개체를 회복합니다.|  
|[WCode](../cpp/com-error-wcode.md)|캡슐화된 `HRESULT`에 매핑되는 16비트 오류 코드를 검색합니다.|  
  
### IErrorInfo 함수  
  
|||  
|-|-|  
|[설명](../cpp/com-error-description.md)|이 `IErrorInfo::GetDescription` 함수 호출|  
|[HelpContext](../cpp/com-error-helpcontext.md)|이 `IErrorInfo::GetHelpContext` 함수 호출|  
|[HelpFile](../cpp/com-error-helpfile.md)|이 `IErrorInfo::GetHelpFile` 함수 호출|  
|[소스](../cpp/com-error-source.md)|이 `IErrorInfo::GetSource` 함수 호출|  
|[GUID](../cpp/com-error-guid.md)|이 `IErrorInfo::GetGUID` 함수 호출|  
  
### 서식 메시지 추출기  
  
|||  
|-|-|  
|[ErrorMessage](../cpp/com-error-errormessage.md)|이 `_com_error` 개체에 저장된 HRESULT에 대한 문자열 메시지를 검색합니다.|  
  
### HRESULT 매퍼를 ExepInfo.wCode  
  
|||  
|-|-|  
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|32비트 `HRESULT`를 16비트 `wCode`에 매핑합니다.|  
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|16비트 `wCode`를 32비트 `HRESULT`로 매핑합니다.|  
  
## Microsoft 전용 종료  
  
## 요구 사항  
 `Header:` comdef.h  
  
 `Lib:` comsuppw.lib or comsuppwd.lib \( [\/Zc:wchar\_t\(wchar\_t를 네이티브 형식으로 인식\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 자세한 내용을 참조하세요.\)  
  
## 참고 항목  
 [컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)   
 [IErrorInfo Interface](http://msdn.microsoft.com/ko-kr/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)