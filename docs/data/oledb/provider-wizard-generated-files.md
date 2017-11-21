---
title: "공급자 마법사가 생성 하는 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 24da0ab4b3ab27cdb9a70c0f9cc05e3ca86e117d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="provider-wizard-generated-files"></a>공급자 마법사가 생성하는 파일
ATL OLE DB 공급자 마법사는 다음 파일을 생성 합니다. 다음 항목에서는 "MyProvider" 짧은 이름을 사용 하지만 정확한 파일 이름을 이름 공급자를 만들 때에 따라 다릅니다.  
  
|파일 이름|설명|  
|---------------|-----------------|  
|MyProviderRS.cpp|포함 된 명령 도우미 `Execute` 메서드와 공급자 열 맵을 합니다.|  
|MyProviderDS.h|데이터 원본 개체를 구현합니다. 이 헤더 파일에는 데이터 원본 속성에 대 한 속성 매핑이 포함 됩니다.|  
|MyProviderRS.h|명령 및 행 집합 개체를 구현합니다. 이 헤더 파일에는 행 집합 및 명령 속성에 대 한 속성 매핑이 포함 됩니다.|  
|MyProviderSess.h|세션 개체를 구현합니다. 이 헤더 파일에는 세션 속성에 대 한 속성 매핑이 포함 됩니다.|  
|MyProvider.rgs|OLE DB 공급자 마법사에 의해 생성 된 등록 된 개체를 포함 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)