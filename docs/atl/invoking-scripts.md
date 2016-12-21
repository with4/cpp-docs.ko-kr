---
title: "Invoking Scripts | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StringRegister"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "스크립트, invoking registry in ATL"
  - "StringRegister method"
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Invoking Scripts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[대체 가능 매개 변수 \(등록자 전처리기\)를 사용 하 여](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) 대체 지도 방법에 대해 설명 하 고 등록자 메서드 언급  **AddReplacement**.  등록자 다른 메서드가 8 특정 스크립트를 있고 모든 다음 표에 설명 되어 있습니다.  
  
|메서드|구문\/설명|  
|---------|------------|  
|**ResourceRegister**|**HRESULT ResourceRegister \(LPCOLESTR**  *resFileName* **, UINT**  `nID` **, LPCOLESTR**  `szType` **\);**<br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 합니다.  *resFileName* 모듈 자체에 대 한 UNC 경로 나타냅니다.  `nID`및 `szType` 리소스의 ID와 형식이 포함 됩니다.|  
|**ResourceUnregister**|**HRESULT ResourceUnregister \(LPCOLESTR**  *resFileName* **, UINT**  `nID` **, LPCOLESTR**  `szType` **\);**<br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 취소 합니다.  *resFileName* 모듈 자체에 대 한 UNC 경로 나타냅니다.  `nID`및 `szType` 리소스의 ID와 형식이 포함 됩니다.|  
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz \(LPCOLESTR**  *resFileName* **, LPCOLESTR**  *szID* **, LPCOLESTR**  `szType` **\);**<br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 합니다.  *resFileName* 모듈 자체에 대 한 UNC 경로 나타냅니다.  *szID* 및 `szType` 리소스의 문자열 식별자 및 형식을 포함 합니다.|  
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz \(LPCOLESTR**  *resFileName* **, LPCOLESTR**  *szID* **, LPCOLESTR**  `szType` **\);**<br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 취소 합니다.  *resFileName* 모듈 자체에 대 한 UNC 경로 나타냅니다.  *szID* 및 `szType` 리소스의 문자열 식별자 및 형식을 포함 합니다.|  
|**FileRegister**|**HRESULT FileRegister \(LPCOLESTR**  *파일 이름이*  **\);**<br /><br /> 스크립트 파일에 등록합니다.  *파일 이름이*  는 UNC 경로를 포함 \(또는\) 리소스 스크립트 파일입니다.|  
|**FileUnregister**|**HRESULT FileUnregister \(LPCOLESTR**  *파일 이름이*  **\);**<br /><br /> 스크립트 파일에서을 등록 취소합니다.  *파일 이름이*  는 UNC 경로를 포함 \(또는\) 리소스 스크립트 파일입니다.|  
|**StringRegister**|**HRESULT StringRegister \(LPCOLESTR**  *데이터*  **\);**<br /><br /> 스크립트에서 문자열을 등록합니다.  *데이터*  는 스크립트를 포함 합니다.|  
|**StringUnregister**|**HRESULT StringUnregister \(LPCOLESTR**  *데이터*  **\);**<br /><br /> 스크립트에서 문자열을 취소합니다.  *데이터*  는 스크립트를 포함 합니다.|  
  
 **ResourceRegisterSz** 및  **ResourceUnregisterSz**와 비슷한  **ResourceRegister** 및  **ResourceUnregister**, 하지만 문자열 식별자를 지정할 수 있습니다.  
  
 메서드  **FileRegister** 및  **FileUnregister** 스크립트 리소스를 사용 하지 않으려면 또는 스크립트 파일 자체에서 원하는 경우 유용 합니다.  메서드  **StringRegister** 및  **StringUnregister** .rgs 파일에 동적으로 할당 된 문자열을 저장할 수 있습니다.  
  
## 참고 항목  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)