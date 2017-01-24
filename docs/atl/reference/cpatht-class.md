---
title: "CPathT Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CPathT"
  - "CPathT"
  - "ATL::CPathT<StringType>"
  - "ATL::CPathT"
  - "ATL.CPathT<StringType>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPathT class"
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
caps.latest.revision: 20
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPathT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 경로 나타냅니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
      template< typename   
      StringType  
      >   
class CPathT  
```  
  
#### 매개 변수  
 `StringType`  
 경로를 사용 하는 ATL\/MFC string 클래스 \(참조  [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)\).  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CPathT::PCXSTR](../Topic/CPathT::PCXSTR.md)|상수 문자열 형식입니다.|  
|[CPathT::PXSTR](../Topic/CPathT::PXSTR.md)|문자열 형식입니다.|  
|[CPathT::XCHAR](../Topic/CPathT::XCHAR.md)|문자 형식입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPathT::CPathT](../Topic/CPathT::CPathT.md)|경로 대 한 생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPathT::AddBackslash](../Topic/CPathT::AddBackslash.md)|경로 대 한 올바른 구문을 만들려면 문자열의 끝에 백슬래시를 추가 하려면이 메서드를 호출 합니다.|  
|[CPathT::AddExtension](../Topic/CPathT::AddExtension.md)|경로에 파일 확장명을 추가 하려면이 메서드를 호출 합니다.|  
|[CPathT::Append](../Topic/CPathT::Append.md)|문자열의 현재 경로를 추가 하려면이 메서드를 호출 합니다.|  
|[CPathT::BuildRoot](../Topic/CPathT::BuildRoot.md)|숫자를 지정 된 드라이브 루트 경로 만들려면이 메서드를 호출 합니다.|  
|[CPathT::Canonicalize](../Topic/CPathT::Canonicalize.md)|경로 정규 형식으로 변환 하려면이 메서드를 호출 합니다.|  
|[CPathT::Combine](../Topic/CPathT::Combine.md)|하나의 패스로 파일 경로 이름을 나타내는 문자열 및 디렉터리 이름을 나타내는 문자열을 연결 하려면이 메서드를 호출 합니다.|  
|[CPathT::CommonPrefix](../Topic/CPathT::CommonPrefix.md)|지정한 경로가 현재 경로와 공통 접두사를 공유 하는지 여부를 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::CompactPath](../Topic/CPathT::CompactPath.md)|파일 경로 타원을 경로 구성 요소를 대체 하 여 지정 된 픽셀 너비에 맞게 잘라내는이 메서드를 호출 합니다.|  
|[CPathT::CompactPathEx](../Topic/CPathT::CompactPathEx.md)|파일 경로 타원을 경로 구성 요소를 대체 하 여 지정 된 문자 수가 내에 맞게 잘라내는이 메서드를 호출 합니다.|  
|[CPathT::FileExists](../Topic/CPathT::FileExists.md)|파일 이름이 경로에 있는지 여부를 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::FindExtension](../Topic/CPathT::FindExtension.md)|파일 확장명 경로 내에서 위치를 찾으려면이 메서드를 호출 합니다.|  
|[CPathT::FindFileName](../Topic/CPathT::FindFileName.md)|파일 이름 경로 내에서 위치를 찾으려면이 메서드를 호출 합니다.|  
|[CPathT::GetDriveNumber](../Topic/CPathT::GetDriveNumber.md)|'A'에서 'Z' 까지의 범위 내에서 드라이브 문자 경로 검색 하 고 해당 드라이브를 반환 하려면이 메서드를 호출 합니다.|  
|[CPathT::GetExtension](../Topic/CPathT::GetExtension.md)|경로에서 파일 확장명을 가져오려면이 메서드를 호출 합니다.|  
|[CPathT::IsDirectory](../Topic/CPathT::IsDirectory.md)|경로 유효한 디렉터리 인지 여부를 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::IsFileSpec](../Topic/CPathT::IsFileSpec.md)|경로 구분 문자에 대 한 경로 검색 하려면이 메서드를 호출 \(예를 들어, ':' 또는 ' \\'\).  경로 구분 문자가 있는 경우 경로 사양 파일 경로가 될 것입니다.|  
|[CPathT::IsPrefix](../Topic/CPathT::IsPrefix.md)|경로 잘못 전달 하 형식 접두사 포함 되어 있는지 여부를 확인 하려면이 메서드를 호출 합니다. `pszPrefix`.|  
|[CPathT::IsRelative](../Topic/CPathT::IsRelative.md)|상대 경로 인지 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::IsRoot](../Topic/CPathT::IsRoot.md)|경로가 디렉터리 루트 인지 여부를 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::IsSameRoot](../Topic/CPathT::IsSameRoot.md)|다른 경로 공통 루트 구성 요소를 현재 경로 있는지 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::IsUNC](../Topic/CPathT::IsUNC.md)|경로 서버에 대 한 올바른 UNC \(범용 명명 규칙\) 경로 인지 여부를 확인 하려면이 메서드를 호출 하 고 공유 합니다.|  
|[CPathT::IsUNCServer](../Topic/CPathT::IsUNCServer.md)|경로 서버에 대 한 올바른 UNC \(범용 명명 규칙\) 경로 인지 여부를 확인 하려면이 메서드를 호출 합니다.|  
|[CPathT::IsUNCServerShare](../Topic/CPathT::IsUNCServerShare.md)|경로가 유효한 UNC \(범용 명명 규칙\) 공유 경로 인지 여부를 확인 하려면이 메서드를 호출 \\\\*server*\\*공유*.|  
|[CPathT::MakePretty](../Topic/CPathT::MakePretty.md)|패스 경로 일관 된 모양으로 모든 소문자를 변환 하려면이 메서드를 호출 합니다.|  
|[CPathT::MatchSpec](../Topic/CPathT::MatchSpec.md)|와일드 카드 일치 유형이 포함 된 문자열에 대 한 경로 검색 하려면이 메서드를 호출 합니다.|  
|[CPathT::QuoteSpaces](../Topic/CPathT::QuoteSpaces.md)|공백이 있으면 경로 따옴표로 묶어야 합니다.이 메서드를 호출 합니다.|  
|[CPathT::RelativePathTo](../Topic/CPathT::RelativePathTo.md)|상대 경로 하나의 파일 또는 폴더를 만들려면이 메서드를 호출 합니다.|  
|[CPathT::RemoveArgs](../Topic/CPathT::RemoveArgs.md)|명령줄 인수에서 경로 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::RemoveBackslash](../Topic/CPathT::RemoveBackslash.md)|경로에서 후행 백슬래시를 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::RemoveBlanks](../Topic/CPathT::RemoveBlanks.md)|경로에서 모든 선행 및 후행 공백을 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::RemoveExtension](../Topic/CPathT::RemoveExtension.md)|있을 경우의 경로에서 파일 확장명을 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::RemoveFileSpec](../Topic/CPathT::RemoveFileSpec.md)|이 경우 뒤에 오는 파일 이름 및 백슬래시는 경로에서 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::RenameExtension](../Topic/CPathT::RenameExtension.md)|새 확장명과 경로에 파일 이름 확장명을 바꾸려면이 메서드를 호출 합니다.  확장명은 파일 이름 확장명이 없는 경우 문자열의 끝에 첨부 됩니다.|  
|[CPathT::SkipRoot](../Topic/CPathT::SkipRoot.md)|드라이브 문자 또는 UNC 공유 서버\/경로 부분을 무시 하는 경로 구문 분석 하는이 메서드를 호출 합니다.|  
|[CPathT::StripPath](../Topic/CPathT::StripPath.md)|정규화 된 경로와 파일 이름의 경로 부분을 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::StripToRoot](../Topic/CPathT::StripToRoot.md)|경로의 루트 정보를 제외한 모든 부품을 제거 하려면이 메서드를 호출 합니다.|  
|[CPathT::UnquoteSpaces](../Topic/CPathT::UnquoteSpaces.md)|시작과 끝 경로에서 따옴표를 제거 하려면이 메서드를 호출 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CPathT::operator const StringType &](../Topic/CPathT::operator%20const%20StringType%20&.md)|이 연산자는 문자열 처럼 처리 하려면 개체가 있습니다.|  
|[CPathT::operator CPathT::PCXSTR](../Topic/CPathT::operator%20CPathT::PCXSTR.md)|이 연산자는 문자열 처럼 처리 하려면 개체가 있습니다.|  
|[CPathT::operator StringType &](../Topic/CPathT::operator%20StringType%20&.md)|이 연산자는 문자열 처럼 처리 하려면 개체가 있습니다.|  
|[CPathT::operator \+\=](../Topic/CPathT::operator%20+=.md)|이 연산자는 문자열의 경로를 추가합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPathT::m\_strPath](../Topic/CPathT::m_strPath.md)|경로입니다.|  
  
## 설명  
 `CPath` `CPathA`, 및 `CPathW` 의 인스턴스화는 `CPathT` 는 다음과 같이 정의:  
  
 `typedef CPathT< CString > CPath;`  
  
 `typedef CPathT< CStringA > CPathA;`  
  
 `typedef CPathT< CStringW > CPathW;`  
  
## 요구 사항  
 **헤더:** atlpath.h  
  
## 참고 항목  
 [클래스](../../atl/reference/atl-classes.md)   
 [CStringT Class](../../atl-mfc-shared/reference/cstringt-class.md)