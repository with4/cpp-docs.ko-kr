---
title: ATL 및 MFC 중에서 선택에 대 한 권장 사항 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 116f2066b98951aa2a470021f5527542ac8cbe46
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>ATL 및 MFC 중에서 선택에 대 한 권장 사항
구성 요소 및 응용 프로그램을 개발할 때는 두 가지 방법 중 선택할 수 있습니다-ATL 및 MFC (Microsoft Foundation Class 라이브러리)입니다.  
  
## <a name="using-atl"></a>ATL을 사용 하 여  
 ATL는 모두 COM 구성 요소 c + +에서 만들고 유지 관리 하는 소형의 신속 하 고 쉬운 방법입니다. ATL을 사용 하 여 컨트롤을 만드는 경우 MFC에서 자동으로 제공 하는 기본 제공 기능이 모두 필요 하지 않습니다.  
  
## <a name="using-mfc"></a>MFC 사용  
 MFC를 사용 하면 전체 응용 프로그램, ActiveX 컨트롤 및 활성 문서를 만들 수 있습니다. Mfc 컨트롤을 이미 만들었으면 MFC의 개발 작업을 계속 하는 것이 좋습니다. 새 컨트롤을 만들 때에 MFC의 기본 제공 기능을 모두 필요 하지 않으면 ATL을 사용 하는 것이 좋습니다.  
  
## <a name="using-atl-in-an-mfc-project"></a>MFC 프로젝트에서 ATL을 사용 하 여  
 기존 MFC 프로젝트에서 ATL을 사용 하 여 마법사를 실행 하 여에 대 한 지원을 추가할 수 있습니다. 자세한 내용은 참조 [MFC 프로젝트에 ATL 지원 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 소개](../atl/introduction-to-atl.md)

