---
title: "emitidl | Microsoft Docs"
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
  - "vc-attr.emitidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "emitidl attribute"
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# emitidl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이후의 모든 IDL 특성 처리 되어 생성 된.idl 파일에 배치 됩니다 여부를 결정 합니다.  
  
## 구문  
  
```  
  
      [ emitidl([boolean],  
   defaultimports=[boolean]  
) ] ;  
```  
  
#### 매개 변수  
 `boolean`  
 Possible values: **true**, **false**, **forced**, **restricted**, **push**, or **pop**.  
  
-   경우  **true**, 소스 코드 파일에서 발견 된 IDL 범주 속성 생성 된.idl 파일에 배치 됩니다.  이 대 한 기본 설정입니다  **emitidl**.  
  
-   경우  **false**, 범주 속성 IDL 소스 코드 파일에서 생성 된.idl 파일에 배치 되지 않습니다.  
  
-   경우  **제한 된**, IDL 특성을 제외 하는 파일에는  [모듈](../windows/module-cpp.md) 특성입니다.  컴파일러는.idl 파일이 생성 되지 않습니다.  
  
-   경우  **강제**, 후속 무시  **제한 된**  에 파일에서 필요 특성이  **모듈** 특성을 파일에 있는 경우 IDL 특성입니다.  
  
-   **밀어넣기**  현재 저장할 수 있습니다  **emitidl**  설정으로 내부  **emitidl**  스택, 및  **pop**  설정할 수 있습니다  **emitidl**  에 위쪽의 내부에 어떤 값이  **emitidl**  스택.  
  
 **defaultimports** *\=* `boolean` \(옵션\)  
 -   경우 `boolean` 입니다  **true**, docobj.idl 생성 된.idl 파일에 가져오기 됩니다.  또한,.idl 파일 이름이 같은 있는.h 파일 경우 `#include` 에 소스 코드.h 파일을 같은 디렉터리에 있는지 다음 생성 된.idl 파일 해당.idl 파일에 대 한 import 문을 포함 합니다.  
  
-   경우 `boolean` 입니다  **false**, docobj.idl 생성 된.idl 파일에 가져올 수 없습니다.  .Idl 파일을 명시적으로 가져오려면 해야 합니다  [가져오기](../windows/import.md).  
  
## 설명  
 다음은  **emitidl** 특성 C\+\+ 소스 코드 파일에서 발견 되 고 범주 IDL 특성은 생성 된.idl 파일에 저장 됩니다.  있으면 없음  **emitidl** 특성, IDL 특성에서 소스 코드 파일에서 생성 된.idl 파일 출력 수 있습니다.  
  
 이 여러 개 있을 수 있습니다  **emitidl** 소스 코드 파일에서 특성.  경우 `[emitidl(false)];` 없이 이후에 파일에서 발생 하는 `[emitidl(true)];`, 특성이 생성 된.idl 파일에 처리 하 고 있습니다.  
  
 컴파일러가 새 파일이 발견 될 때마다  **emitidl** 암시적으로 설정 된  **true**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치에|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)