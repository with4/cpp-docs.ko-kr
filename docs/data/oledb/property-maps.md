---
title: "속성 맵 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 05bd576e6e55c94306a8dd648c57a4d606bed696
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="property-maps"></a>속성 맵
세션, 행 집합 및 선택적 명령 개체 외에도 각 공급자는 하나 이상의 속성을 지원합니다. 이러한 속성은 OLE DB 공급자 마법사에서 생성 된 헤더 파일에 포함 된 속성 매핑이에 정의 됩니다. 각 헤더 파일에는 개체 또는 해당 파일에 정의 된 개체에 대해 정의 된 OLE DB 속성 그룹의 속성에 대 한 맵을 포함 합니다. 데이터 원본 개체를 포함 하는 헤더 파일에 대 한 속성 매핑이 포함 된 [DataSource 속성](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx)합니다. Session.h에 대 한 속성 매핑이 포함 된 [세션 속성](https://msdn.microsoft.com/en-us/library/ms714221.aspx)합니다. 행 집합 및 명령 개체 라는 단일 헤더 파일에 있는 *projectname*RS.h 합니다. 이러한 속성은의 멤버는 [행 집합 속성](https://msdn.microsoft.com/en-us/library/ms711252.aspx) 그룹입니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)