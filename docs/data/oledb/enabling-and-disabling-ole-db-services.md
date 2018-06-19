---
title: 사용 하도록 설정 및 OLE DB 서비스 사용 안 함 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 785997cafec76bfa438382ace6930d53c31c4dc9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099474"
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB 서비스 사용 및 사용 안 함
OLE DB 서비스 구성 요소 관리자는 개별 서비스 구성 요소는 소비자가 요청한 확장 된 기능을 충족 하기 위해 호출 될 수 있는지 여부를 확인 하려면 공급자에서 지 원하는를 소비자에 의해 지정 된 속성을 비교 합니다. 예를 들어 응용 프로그램이 스크롤 가능 커서를 요청 하는 경우 공급자는 정방향 전용 커서 지원 서비스 구성 요소 관리자 스크롤할 수 있는 기능을 제공 하도록 Client Cursor Engine 서비스 구성 요소를 호출 합니다. 응용 프로그램은 공급자의 행 집합에서 기본적으로 지원 되는 확장 된 기능에 의존 하므로 응용 프로그램은 기능을 기능 수에 나타나지 클라이언트에 의해 반환 된 행 집합을 요청 하기 위한 속성을 명시적으로 설정 하지 않는 경우 커서 엔진입니다. 상호 운용성을 위해 응용 프로그램은 항상 설정 속성 확장 된 기능을 명시적으로 요청 필요한 경우.  
  
 일부 경우에는 공급자의 특성에 대 한 가정을 확인 하는 기존 응용 프로그램에서 작동 하도록 개별 OLE DB 서비스를 사용 하지 않도록 설정 해야 할 수도 있습니다. OLE DB 서비스는 개별 서비스 또는 연결 하 여 연결 하거나 단일 공급자를 사용 하 여 모든 응용 프로그램에 대 한 모든 서비스를 비활성화 하는 기능을 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 리소스 풀링 및 서비스](../../data/oledb/ole-db-resource-pooling-and-services.md)