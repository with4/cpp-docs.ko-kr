---
title: CAtlServiceModuleT::Handler 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
dev_langs:
- C++
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0c0386cd17e7a33628790520e356c706f9743b9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT::Handler 함수
`CAtlServiceModuleT::Handler` 서비스 제어 관리자 (SCM) 호출 하는 서비스의 상태를 검색 하 고 (예: 중지 또는 일시 중지) 다양 한 지침을 제공 하는 루틴입니다. SCM가 작업 코드에 전달 `Handler` 를 나타내는 서비스에서 수행 해야 합니다. 기본 ATL 생성 서비스 stop 명령이 처리 됩니다. SCM stop 명령이 통과 되 면 서비스 지시 SCM 프로그램이 중지 되려고 합니다. 서비스 호출 `PostThreadMessage` 를 자신에 게 종료 메시지를 게시 합니다. 메시지 루프를 종료 하 고 서비스가 종료 됩니다.  
  
 자세한 지침을 처리 하려면 변경 해야는 `m_status` 데이터 멤버의 초기화는 `CAtlServiceModuleT` 생성자입니다. 이 데이터 멤버 SCM 서비스 제어판 응용 프로그램에서 서비스를 선택한 경우 사용할 수 있도록 단추를 알려 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스](../atl/atl-services.md)   
 [CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

