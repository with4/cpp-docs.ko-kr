---
title: "OLE 백그라운드: 연결 및 포함 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE embedded items [MFC]
- item types [MFC], defined
- item types [MFC]
- OLE [MFC], linked items
- linked items (OLE) [MFC]
- embedded objects [MFC]
- OLE items [MFC], types
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d9b7de075b3c32d130639c60c7fcc389ae37da54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background-linking-and-embedding"></a>OLE 백그라운드: 연결 및 포함
컨테이너 응용 프로그램에서 붙여넣기 명령을 사용하면 포함된 구성 요소 또는 포함된 항목을 만들 수 있습니다. 포함된 항목에 대한 소스 데이터는 이를 포함하는 OLE 문서의 일부로 저장됩니다. 이 방식으로 워드 프로세서 문서에 대한 문서 파일은 텍스트를 포함하고, 비트맵, 그래프, 공식 또는 다른 모든 종류의 데이터를 포함할 수도 있습니다.  
  
 OLE는 다른 응용 프로그램의 데이터를 포함할 수 있는 또 다른 방법인 링크된 구성 요소 또는 링크된 항목 또는 링크를 만드는 방법을 제공합니다. 링크된 항목을 만드는 단계는 붙여넣기 명령 대신 링크 붙여넣기 명령을 사용하는 것을 제외하고는 포함된 항목을 만들 때와 비슷합니다. 포함된 구성 요소와 달리 링크된 구성 요소는 종종 개별 파일로 존재하는 원본 데이터에 대한 경로를 저장합니다.  
  
 예를 들어 워드 프로세서 문서를 작업 중일 때 일부 스프레드시트 셀에 대한 링크된 항목을 만들면, 링크된 항목에 대한 데이터가 원본 스프레드시트 문서에 저장됩니다. 워드프로세서 문서에는 해당 항목을 찾을 수 있는 위치를 지정하는 정보만 포함됩니다. 즉, 원본 스프레드시트 문서에 대한 링크가 포함됩니다. 셀을 두 번 클릭하면 스프레드시트 응용 프로그램이 실행되고 원본 스프레드시트 문서가 원래 저장되었던 위치에서 로드됩니다.  
  
 포함 또는 링크 여부에 관계없이 모든 OLE 항목은 해당 항목을 만든 응용 프로그램에 따라 연결된 형식을 갖습니다. 예를 들어 Microsoft 그림판 항목과 Microsoft Excel 항목은 각자 다른 한 가지 항목 형식입니다. 하지만 일부 응용 프로그램에서는 두 개 이상의 항목 형식을 만들 수 있습니다. 예를 들어 Microsoft Excel은 워크시트 항목, 차트 항목 및 매크로시트 항목을 만들 수 있습니다. 각이 항목의 고유 하 게 식별할 수 클래스 식별자를 사용 하 여 시스템 또는 **CLSID**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE 백그라운드](../mfc/ole-background.md)   
 [OLE 백그라운드: 컨테이너 및 서버](../mfc/ole-background-containers-and-servers.md)   
 [컨테이너: 클라이언트 항목](../mfc/containers-client-items.md)   
 [서버: 서버 항목](../mfc/servers-server-items.md)

