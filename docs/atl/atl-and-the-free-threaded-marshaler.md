---
title: ATL 및 자유 스레드된 마샬러 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1716985adf65b714a418f20d3873f45c32d368b4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL 및 자유 스레드된 마샬러
ATL 단순 개체 마법사의 속성 페이지 (FTM) 자유 스레드된 마샬러를 집계 하 여 클래스를 허용 하는 옵션을 제공 합니다.  
  
 마법사에서 자유 스레드된 마샬러의 인스턴스를 만드는 코드를 생성 `FinalConstruct` 에서 해당 인스턴스를 해제 하 고 `FinalRelease`합니다. A `COM_INTERFACE_ENTRY_AGGREGATE` 매크로 되도록 COM 맵을에 자동으로 추가 `QueryInterface` 에 대 한 요청 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707) 자유 스레드된 마샬러에 의해 처리 됩니다.  
  
 자유 스레드된 마샬러 직접 액세스할을 수 개체의 인터페이스에 동일한 프로세스의 모든 스레드에서 아파트 간 호출 속도가 빨라집니다. 이 옵션은 모두 스레딩 모델을 사용 하는 클래스에 대 한 것입니다.  
  
 이 옵션을 사용할 경우 클래스는 데이터의 스레드 보안에 대 한 책임을 져야 합니다. 또한 자유 스레드된 마샬러를 집계 하 고 다른 개체에서 가져온 인터페이스 포인터를 사용 해야 하는 개체는 인터페이스 올바르게 마샬링 되므로 추가 단계를 수행 해야 합니다. 일반적으로이 전역 인터페이스 테이블 (GIT)에서 인터페이스 포인터를 저장 하 고 사용 될 때마다 GIT에서 포인터를 가져오는 해야 합니다. 클래스를 제공 하는 ATL [CComGITPtr](../atl/reference/ccomgitptr-class.md) GIT에 저장 된 인터페이스 포인터를 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [전역 인터페이스 테이블을 사용 하는 경우](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [프로세스 서버 스레딩 문제](http://msdn.microsoft.com/library/windows/desktop/ms687205)

