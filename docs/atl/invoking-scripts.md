---
title: "스크립트 (ATL) 호출 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: StringRegister
dev_langs: C++
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c1fc6893b02dccff6bb30d7a20d1a2c1dce9fbb1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="invoking-scripts"></a>스크립트 호출
[대체 가능 매개 변수 (The 등록자 전처리기)를 사용 하 여](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) 대체 지도 설명 하 고 등록 방법에 언급 **AddReplacement**합니다. 등록자 스크립트에 다른 메서드를 8 개 있으며 다음 표에 설명 된 모든.  
  
|메서드|구문/설명|  
|------------|-------------------------|  
|**ResourceRegister**|**HRESULT ResourceRegister (LPCOLESTR***resFileName* **, UINT** `nID` **, LPCOLESTR** `szType` **);** <br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 합니다. *resFileName* UNC 경로 모듈 자체를 나타냅니다. `nID`및 `szType` 각각 리소스의 ID 및 형식을 포함 합니다.|  
|**ResourceUnregister**|**HRESULT ResourceUnregister (LPCOLESTR***resFileName* **, UINT** `nID` **, LPCOLESTR** `szType` **);** <br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 취소 합니다. *resFileName* UNC 경로 모듈 자체를 나타냅니다. `nID`및 `szType` 각각 리소스의 ID 및 형식을 포함 합니다.|  
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);** <br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 합니다. *resFileName* UNC 경로 모듈 자체를 나타냅니다. *szID* 및 `szType` 리소스의 문자열 식별자 및 형식, 각각 포함 합니다.|  
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);** <br /><br /> 모듈의 리소스에 포함 된 스크립트를 등록 취소 합니다. *resFileName* UNC 경로 모듈 자체를 나타냅니다. *szID* 및 `szType` 리소스의 문자열 식별자 및 형식, 각각 포함 합니다.|  
|**FileRegister**|**HRESULT FileRegister (LPCOLESTR***fileName***);** <br /><br /> 파일에 스크립트를 등록합니다. *fileName* 포함 (또는) 리소스 스크립트 파일에 UNC 경로입니다.|  
|**FileUnregister**|**HRESULT FileUnregister (LPCOLESTR***fileName***);** <br /><br /> 파일에 스크립트 등록을 취소합니다. *fileName* 포함 (또는) 리소스 스크립트 파일에 UNC 경로입니다.|  
|**StringRegister**|**HRESULT StringRegister (LPCOLESTR***데이터***);** <br /><br /> 문자열에는 스크립트를 등록합니다. *데이터* 스크립트 자체를 포함 합니다.|  
|**StringUnregister**|**HRESULT StringUnregister (LPCOLESTR***데이터***);** <br /><br /> 문자열에 스크립트 등록을 취소합니다. *데이터* 스크립트 자체를 포함 합니다.|  
  
 **ResourceRegisterSz** 및 **ResourceUnregisterSz**, 비슷합니다 **ResourceRegister** 및 **ResourceUnregister**를 지정할 수 있도록 하지만 문자열 식별자입니다.  
  
 메서드 **FileRegister** 및 **FileUnregister** 는 해당 파일에 스크립트 또는 스크립트 리소스의 않도록 하려는 경우 유용 합니다. 메서드 **StringRegister** 및 **StringUnregister** .rgs 파일을 동적으로 할당 된 문자열에 저장할 수 있도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [등록자 스크립트 만들기](../atl/creating-registrar-scripts.md)

