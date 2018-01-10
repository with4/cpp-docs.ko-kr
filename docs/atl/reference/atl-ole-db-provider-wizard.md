---
title: "ATL OLE DB 공급자 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.provider.overview
dev_langs: C++
helpviewer_keywords:
- ATL OLE DB Provider Wizard
- ATL projects, adding ATL OLE DB providers
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 660f70be8ec4ac1efcec056c694d0e2fc3256071
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-ole-db-provider-wizard"></a>ATL OLE DB 공급자 마법사
이 마법사에서 OLE DB 공급자를 구성 하는 클래스를 만듭니다.  
  
## <a name="remarks"></a>설명  
 Visual Studio 2008부터,이 마법사에서 생성 하는 등록 스크립트는 해당 COM 구성 요소 등록에서 **HKEY_CURRENT_USER** 대신 **HKEY_LOCAL_MACHINE**합니다. 이 동작을 수정 하려면 설정는 **모든 사용자에 대 한 구성 요소 등록** ATL 마법사의 옵션입니다.  
  
 다음 표에서 ATL OLE DB 공급자 마법사에 대 한 옵션을 설명합니다.  
  
 **짧은 이름**  
 만들어질 공급자의 약식 이름을 입력 합니다. 다른 입력란 마법사에서 자동으로 채워집니다. 입력에 기반 합니다. 원하는 경우 다른 이름 상자를 편집할 수 있습니다.  
  
 **Coclass**  
 Coclass의 이름입니다. 이 이름과 일치 하도록 ProgID 이름이 변경 됩니다.  
  
 **특성 사용**  
 이 옵션은 특성 또는 서식 파일 정의 사용 하 여 공급자 클래스를 만들 있는지 여부를 지정 합니다. 이 옵션을 선택 하면 마법사 (이 기본 옵션 특성 사용된 프로젝트를 만든 경우) 하는 템플릿 선언 대신 특성을 사용 합니다. 이 옵션의 선택을 취소 (이 기본 옵션 이외의 특성 사용 프로젝트를 만든 경우) 하는 특성 대신 템플릿 선언을 사용 합니다.  
  
 비-특성을 사용 하는 프로젝트를 만들 때이 옵션을 선택 하면 프로젝트를 특성 사용된 프로젝트를 변환 하 고 계속할지 여부를 묻는 마법사 경고 합니다.  
  
 **ProgID**  
 ProgID 또는 프로그래밍 방식 식별자에는 응용 프로그램에서 GUID 대신 사용할 수 있는 텍스트 문자열입니다. ProgID 이름은 *Projectname.Coclassname*합니다.  
  
 **Version**  
 공급자의 버전 번호입니다. 기본값은 1입니다.  
  
 **DataSource 클래스**  
 데이터 소스 클래스 C 양식의 이름*Shortname*소스입니다.  
  
 **데이터 원본.h 파일**  
 데이터 원본 클래스에 대 한 헤더 파일입니다. 이 파일의이 이름을 편집 하거나 기존 헤더 파일을 선택할 수 있습니다.  
  
 **세션 클래스**  
 C 형식의 세션 클래스의 이름*Shortname*세션입니다.  
  
 **세션.h 파일**  
 세션 클래스에 대 한 헤더 파일입니다. 이 파일의이 이름을 편집 하거나 기존 헤더 파일을 선택할 수 있습니다.  
  
 **명령 클래스**  
 형식 C의 명령 클래스의 이름*Shortname*명령입니다.  
  
 **명령.h 파일**  
 명령 클래스에 대 한 헤더 파일입니다. 이 이름은 편집할 수 없습니다 하며 행 집합 헤더 파일의 이름에 따라 달라 집니다.  
  
 **행 집합 클래스**  
 행 집합 클래스 C 양식의 이름*Shortname*행 집합입니다.  
  
 **행 집합.h 파일**  
 행 집합 클래스에 대 한 헤더 파일입니다. 이 파일의이 이름을 편집 하거나 기존 헤더 파일을 선택할 수 있습니다.  
  
 **행 집합.cpp 파일**  
 공급자의 구현 파일입니다. 이 파일의이 이름을 편집 하거나 기존 구현 파일을 선택할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL OLE DB 공급자](../../atl/reference/adding-an-atl-ole-db-provider.md)

