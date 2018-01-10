---
title: "ASP, ATL Active Server Page 구성 요소 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.asp.asp
dev_langs: C++
helpviewer_keywords: ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69d3837cc0996c0e0e0784214cfbfa6744afbf94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP, ATL Active Server Page 구성 요소 마법사
ATL Active Server 페이지 구성 요소 마법사의이 페이지를 사용 하 여 ASP 구성 요소와 관련 된 상태 및 정보 처리에 대 한 선택적 설정을 지정 합니다.  
  
 **선택적 메서드**  
 선택적 ASP 메서드 추가 **OnStartPage** 및 **OnEndPage**, 개체에 있습니다. Active Server Pages 내장 개체를 설정 하려면이 옵션을 선택 해야 합니다. 기본적으로 선택 됩니다.  
  
-   **OnStartPage/OnEndPage** [OnStartPage](https://msdn.microsoft.com/library/ms691624.aspx) 스크립트 개체에 액세스 하려고 처음으로 호출 됩니다. **OnEndPage** 개체가 완료 되 면 호출 되는 스크립트를 처리 합니다.  
  
 **내장 개체**  
 선택 해야 합니다는 **OnStartPage/OnEndPage** ASP 내장 개체를 설정할 옵션입니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**요청**|Active Server Pages 내장 함수에 액세스할 수 **요청** 개체입니다. HTTP 요청을 전달 하는 요청 개체가 사용 됩니다.|  
|**응답**|Active Server Pages 내장 함수에 액세스할 수 **응답** 개체입니다. 요청에 대 한 응답으로 응답 개체 정보를 사용자에 게 표시 하도록 브라우저를 보냅니다.|  
|**세션**|Active Server Pages 내장 함수에 액세스할 수 **세션** 개체입니다. **세션** 개체 저장 및 검색 상태 정보를 포함 하 여 현재 사용자 세션에 대 한 정보를 유지 관리 합니다.|  
|**응용 프로그램**|Active Server Pages 내장 함수에 액세스할 수 **응용 프로그램** 개체입니다. **응용 프로그램** 개체는 여러 ASP 개체 간에 공유 되는 상태를 관리 합니다.|  
|**서버**|Active Server Pages 내장 함수에 액세스할 수 **서버** 개체입니다. **서버** 개체를 사용 하면 다른 ASP 개체를 만들 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [ATL Active Server Page 구성 요소 마법사](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page 구성 요소](../../atl/reference/adding-an-atl-active-server-page-component.md)

