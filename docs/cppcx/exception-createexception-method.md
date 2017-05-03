---
title: "Exception::CreateException 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::CreateException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::CreateException 메서드"
ms.assetid: 70e72bb4-3fec-478d-af3d-9ec8762d2825
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::CreateException 메서드
지정된 HRESULT 값에서 Platform::Exception^을 만듭니다.  
  
## 구문  
  
```cpp  
Exception^ CreateException(int32 hr)  
Exception^ CreateException(int32 hr, Platform::String^ message)  
```  
  
## 매개 변수  
 hr  
 일반적으로 COM 메서드 호출에서 가져오는 HRESULT 값입니다. 값이 0\(S\_OK와 같음\)인 경우, 성공하는 COM 메서드는 예외를 throw해서는 안 되므로 이 메서드는 [Platform::InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md)을 throw합니다.  
  
 message  
 오류를 설명하는 문자열입니다.  
  
## 반환 값  
 오류 HRESULT를 나타내는 예외입니다.  
  
## 설명  
 예를 들어 COM 인터페이스 메서드에 대한 호출에서 반환되는 HRESULT에서 예외를 만들려면 이 메서드를 사용합니다. String^ 매개 변수를 사용하는 오버로드를 사용하여 사용자 지정 메시지를 제공할 수 있습니다.  
  
 단순히 HRESULT를 포함하는 [Platform::COMException](../cppcx/platform-comexception-class.md)을 만드는 대신 CreateException을 사용하여 강력한 형식의 예외를 만드는 것이 좋습니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)