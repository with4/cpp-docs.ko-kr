---
title: "CUrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CUrl"
  - "CUrl"
  - "ATL::CUrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUrl class"
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CUrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 URL을 나타냅니다.  기존 URL을 구문 분석 하는 여부와 독립적으로 다른 URL의 각 요소를 조작할 수 있습니다 문자열 또는 문자열 처음부터 새로 작성 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CUrl  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CUrl::CUrl](../Topic/CUrl::CUrl.md)|생성자입니다.|  
|[CUrl::~CUrl](../Topic/CUrl::~CUrl.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CUrl::Canonicalize](../Topic/CUrl::Canonicalize.md)|URL 문자열을 정규 형식으로 변환 하려면이 메서드를 호출 합니다.|  
|[CUrl::Clear](../Topic/CUrl::Clear.md)|URL 필드를 모두 지우려면이 메서드를 호출 합니다.|  
|[CUrl::CrackUrl](../Topic/CUrl::CrackUrl.md)|디코딩할 URL을 구문 분석 하 고이 메서드를 호출 합니다.|  
|[CUrl::CreateUrl](../Topic/CUrl::CreateUrl.md)|URL을 만들려면이 메서드를 호출 합니다.|  
|[CUrl::GetExtraInfo](../Topic/CUrl::GetExtraInfo.md)|추가 정보를 얻으려면이 메서드를 호출 \(예:?*텍스트* 또는 \#*텍스트*\)의 url입니다.|  
|[CUrl::GetExtraInfoLength](../Topic/CUrl::GetExtraInfoLength.md)|길이 추가 정보를 얻으려면이 메서드를 호출 \(예:?*텍스트* 또는 \#*텍스트*\)에서 URL을 검색 합니다.|  
|[CUrl::GetHostName](../Topic/CUrl::GetHostName.md)|URL에서 호스트 이름을 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetHostNameLength](../Topic/CUrl::GetHostNameLength.md)|호스트 이름의 길이를 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetPassword](../Topic/CUrl::GetPassword.md)|URL에서 암호를 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetPasswordLength](../Topic/CUrl::GetPasswordLength.md)|암호의 길이 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetPortNumber](../Topic/CUrl::GetPortNumber.md)|이 포트 번호에서 ATL\_URL\_PORT이 메서드를 호출 합니다.|  
|[CUrl::GetScheme](../Topic/CUrl::GetScheme.md)|URL 구성표 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetSchemeName](../Topic/CUrl::GetSchemeName.md)|URL 구성표 이름을 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetSchemeNameLength](../Topic/CUrl::GetSchemeNameLength.md)|URL 구성표 이름 길이 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetUrlLength](../Topic/CUrl::GetUrlLength.md)|URL 길이 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetUrlPath](../Topic/CUrl::GetUrlPath.md)|URL 경로 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetUrlPathLength](../Topic/CUrl::GetUrlPathLength.md)|URL 경로 길이 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetUserName](../Topic/CUrl::GetUserName.md)|URL에서 사용자 이름을 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetUserNameLength](../Topic/CUrl::GetUserNameLength.md)|사용자 이름의 길이를 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::SetExtraInfo](../Topic/CUrl::SetExtraInfo.md)|추가 정보를 설정 하려면이 메서드를 호출 \(예:?*텍스트* 또는 \#*텍스트*\)의 URL입니다.|  
|[CUrl::SetHostName](../Topic/CUrl::SetHostName.md)|호스트 이름을 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetPassword](../Topic/CUrl::SetPassword.md)|암호를 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetPortNumber](../Topic/CUrl::SetPortNumber.md)|ATL\_URL\_PORT에서 포트 번호를 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetScheme](../Topic/CUrl::SetScheme.md)|URL 구성표를 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetSchemeName](../Topic/CUrl::SetSchemeName.md)|URL 구성표 이름을 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetUrlPath](../Topic/CUrl::SetUrlPath.md)|URL 경로 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetUserName](../Topic/CUrl::SetUserName.md)|사용자 이름을 설정 하려면이 메서드를 호출 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CUrl::operator \=](../Topic/CUrl::operator%20=.md)|지정한 할당 `CUrl` 개체에는 현재 `CUrl` 개체입니다.|  
  
## 설명  
 `CUrl`URL, 경로 또는 포트 번호 등의 필드를 조작할 수 있습니다.  `CUrl`다음 형식의 Url을 인식합니다.  
  
 \<Scheme\>: \/ \/ \<UserName\>: \<Password\> @ \<HostName\>: \<PortNumber\> \/ \<UrlPath\> \<ExtraInfo\>  
  
 \(일부 필드는 선택 사항입니다.\) 예를 들어이 URL을 고려 하십시오.  
  
 http:\/\/someone:secret@www.microsoft.com:80\/visualc\/stuff.htm\#contents  
  
 [CUrl::CrackUrl](../Topic/CUrl::CrackUrl.md) 는 다음과 같이 구문 분석 합니다.  
  
-   구성표: "http" 또는  [ATL\_URL\_SCHEME\_HTTP](../Topic/ATL_URL_SCHEME.md)  
  
-   사용자 이름: "사람"  
  
-   "암호" 암호:  
  
-   호스트 이름: "www.microsoft.com"  
  
-   향하는: 80  
  
-   UrlPath: "visualc\/stuff.htm"  
  
-   ExtraInfo: "\#contents"  
  
 UrlPath 필드 \(예를 들어\) 조작할 수 있습니다  [GetUrlPath](../Topic/CUrl::GetUrlPath.md),  [GetUrlPathLength](../Topic/CUrl::GetUrlPathLength.md), 및  [SetUrlPath](../Topic/CUrl::SetUrlPath.md).  사용 하면  [CreateUrl](../Topic/CUrl::CreateUrl.md) 전체 URL 문자열을 만들 수 있습니다.  
  
## 요구 사항  
 **헤더:** atlutil.h  
  
## 참고 항목  
 [클래스](../../atl/reference/atl-classes.md)