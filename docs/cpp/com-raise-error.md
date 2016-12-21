---
title: "_com_raise_error | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_raise_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_raise_error 함수"
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_raise_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 오류에 대한 응답으로 [\_com\_error](../cpp/com-error-class.md)를 throw합니다.  
  
## 구문  
  
```  
  
      void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### 매개 변수  
 `hr`  
 `HRESULT` 정보입니다.  
  
 `perrinfo`  
 **IErrorInfo** 개체입니다.  
  
## 설명  
 comdef.h에서 정의된 `_com_raise_error`는 동일한 이름과 프로토타입의 사용자 작성 버전으로 교체할 수 있습니다.  이는 `#import`를 사용하고 C\+\+ 예외 처리는 사용하지 않으려는 경우 실행할 수 있습니다.  이 경우 **\_com\_raise\_error**의 사용자 버전에서 `longjmp`를 실행하기로 결정할 수도 있고 메시지 상자를 표시하고 중지할 수도 있습니다.  컴파일러 COM 지원 코드가 반환을 예상하고 있지 않기 때문에 사용자 버전은 반환할 수 없습니다.  
  
 또한 [\_set\_com\_error\_handler](../cpp/set-com-error-handler.md)를 사용하여 기본 오류 처리 함수를 대체할 수도 있습니다.  
  
 기본적으로 `_com_raise_error`는 다음과 같이 정의됩니다.  
  
```  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
## Microsoft 전용 종료  
  
## 요구 사항  
 **헤더:** comdef.h  
  
 **Lib:** "wchar\_t is Native Type" 컴파일러 옵션이 설정되어 있는 경우 comsuppw.lib 또는 comsuppwd.lib를 사용합니다.  "wchar\_t is Native Type"이 해제되어 있는 경우 comsupp.lib를 사용합니다.  자세한 내용은 [\/Zc:wchar\_t\(wchar\_t를 네이티브 형식으로 인식\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)을 참조하십시오.  
  
## 참고 항목  
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)   
 [\_set\_com\_error\_handler](../cpp/set-com-error-handler.md)