---
title: "ATL 클래스에 ActiveX 컨트롤 포함 용이? | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
ms.assetid: 803a4605-7f4c-4139-8638-49d8783d31b0
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0346f362dac7a184691feac4a8dab25f5709e095
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="which-atl-classes-facilitate-activex-control-containment"></a>ATL 클래스에 ActiveX 컨트롤 포함 용이?
ATL의 컨트롤 호스팅 코드 모든 ATL 클래스;를 사용 하도록 요구 하지 않습니다. 간단히 만들 수 있습니다는 **"AtlAxWin80"** 창 및 필요한 경우 컨트롤 호스팅 API 사용 하 여 (자세한 내용은 참조 **ATL 컨트롤 호스팅 API를 이란**합니다. 그러나 다음 클래스의 포함 기능 사용 하기 쉽도록 합니다.  
  
|클래스|설명|  
|-----------|-----------------|  
|[CAxWindow](../atl/reference/caxwindow-class.md)|래핑하는 **"AtlAxWin80"** 창에서 창을 만드는 컨트롤 만들기 및/또는 창으로 컨트롤을 연결 및 호스트 개체에서 인터페이스 포인터를 검색 하기 위한 메서드를 제공 합니다.|  
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|래핑하는 **"AtlAxWinLic80"** 창에서 창을 만드는, 컨트롤 만들기 및/또는 창에 라이센스가 있는 컨트롤을 연결 및 개체에 대 한 인터페이스 포인터를 검색 하기 위한 메서드를 제공 합니다.|  
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|대화 상자 리소스를 기반으로 하는 ActiveX 컨트롤 클래스에 대 한 기본 클래스 역할을 합니다. 이러한 컨트롤에는 다른 ActiveX 컨트롤 포함 될 수 있습니다.|  
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|대화 상자 리소스를 기반으로 하는 대화 상자 클래스에 대 한 기본 클래스 역할을 합니다. 이러한 대화 상자에 ActiveX 컨트롤 포함 될 수 있습니다.|  
|[CWindow](../atl/reference/cwindow-class.md)|메서드를 제공 [GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol), 호스트 창이의 ID를 지정 된 컨트롤에 대 한 인터페이스 포인터 반환 합니다. Windows API 래퍼에 의해 노출 되는 또한 `CWindow` 일반적으로 창 관리를 보다 쉽게 확인 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤 포함 FAQ](../atl/atl-control-containment-faq.md)

