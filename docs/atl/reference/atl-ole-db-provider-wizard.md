---
title: "ATL OLEDB 공급자 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.provider.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL OLEDB 공급자 마법사"
  - "ATL 프로젝트, ATL OLE DB 공급자 추가"
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# ATL OLEDB 공급자 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 마법사에서는 OLE DB 공급자를 구성하는 클래스를 만듭니다.  
  
## 설명  
 [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)]부터는 이 마법사에서 생성되는 등록 스크립트를 통해 해당 COM 구성 요소가 **HKEY\_LOCAL\_MACHINE** 대신 **HKEY\_CURRENT\_USER**에 등록됩니다.  이 동작을 수정하려면 ATL 마법사의 **모든 사용자의 구성 요소 등록** 옵션을 설정합니다.  
  
 다음 표에서는 ATL OLE DB 공급자 마법사에 대한 옵션을 설명합니다.  
  
 **약식 이름**  
 만들려는 공급자의 약식 이름을 입력합니다.  입력한 내용은 마법사의 다른 입력란에 자동으로 들어갑니다.  필요한 경우 다른 이름 상자를 편집할 수 있습니다.  
  
 **Coclass**  
 coclass의 이름입니다.  이 이름과 일치하도록 ProgID 이름이 변경됩니다.  
  
 **특성 사용**  
 이 옵션은 특성 또는 템플릿 선언 중 어느 것을 사용하여 공급자 클래스를 만들 것인지 지정합니다.  이 옵션을 선택하면 템플릿 선언 대신 특성이 사용됩니다. 특성을 사용하는 프로젝트의 기본값입니다.  이 옵션의 선택을 취소하면 특성 대신 템플릿 선언이 사용됩니다. 특성을 사용하지 않는 프로젝트의 기본값입니다.  
  
 특성을 사용하지 않는 프로젝트에 대해 이 옵션을 선택하면 프로젝트가 특성을 사용하는 프로젝트로 변환될 것이라는 경고와 함께 계속할지를 묻는 메시지가 표시됩니다.  
  
 **ProgID**  
 ProgID 또는 프로그램 식별자는 응용 프로그램에서 GUID 대신 사용할 수 있는 텍스트 문자열입니다.  ProgID 이름은 *Projectname*.*Coclassname* 형식을 취합니다.  
  
 **버전**  
 공급자의 버전 번호입니다.  기본값은 1입니다.  
  
 **데이터 소스**  
 C`Shortname` Source 형식의 데이터 소스 클래스의 이름입니다.  
  
 **데이터 소스 .h 파일**  
 데이터 소스 클래스의 헤더 파일입니다.  이 파일의 이름을 편집하거나 기존 헤더 파일을 선택할 수 있습니다.  
  
 **세션 클래스**  
 C`Shortname`Session 형식의 세션 클래스 이름입니다.  
  
 **세션 .h 파일**  
 세션 클래스의 헤더 파일입니다.  이 파일의 이름을 편집하거나 기존 헤더 파일을 선택할 수 있습니다.  
  
 **명령 클래스**  
 C`Shortname`Command 형식의 명령 클래스 이름입니다.  
  
 **명령 .h 파일**  
 명령 클래스의 헤더 파일입니다.  이 이름은 편집할 수 없으며 행 집합 헤더 파일에 따라 결정됩니다.  
  
 **행 집합 클래스**  
 C`Shortname`Rowset 형식의 행 집합 클래스의 이름입니다.  
  
 **행 집합 .h 파일**  
 행 집합 클래스의 헤더 파일입니다.  이 파일의 이름을 편집하거나 기존 헤더 파일을 선택할 수 있습니다.  
  
 **행 집합 .cpp 파일**  
 공급자의 구현 파일입니다.  이 파일의 이름을 편집하거나 기존 구현 파일을 선택할 수 있습니다.  
  
## 참고 항목  
 [ATL OLE DB Provider](../../atl/reference/adding-an-atl-ole-db-provider.md)