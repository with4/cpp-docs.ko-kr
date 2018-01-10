---
title: "ATL 유틸리티 참조 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69f085df8b5dadbd0ba9d20596d37cb6313bb3f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-utilities-reference"></a>ATL 유틸리티 참조
형식의 경로 Url을 조작 하기 위한 코드를 제공 하는 ATL [CPathT](../atl/reference/cpatht-class.md) 및 [CUrl](../atl/reference/curl-class.md)합니다. 스레드 풀 [CThreadPool](../atl/reference/cthreadpool-class.md), 응용 프로그램에서 사용할 수 있습니다. 이 코드는 atlpath.h 및 atlutil.h에서 찾을 수 있습니다.  
  
### <a name="classes"></a>클래스  
  
|||  
|-|-|  
|[CPathT 클래스](../atl/reference/cpatht-class.md)|이 클래스는 경로 나타냅니다.|  
|[CDebugReportHook 클래스](../atl/reference/cdebugreporthook-class.md)|이 클래스를 사용 하 여 명명된 된 파이프에 디버그 보고서를 보내도록 합니다.|  
|[CNonStatelessWorker 클래스](../atl/reference/cnonstatelessworker-class.md)|스레드 풀의 요청을 수신 하 고 각 요청에 대해 생성 되 고 제거 하는 작업자 개체로 전달 합니다.|  
|[CNoWorkerThread 클래스](../atl/reference/cnoworkerthread-class.md)|이 클래스를 사용 하 여에 대 한 인수로 `MonitorClass` 동적 캐시 유지 관리를 사용 하지 않도록 설정 하려는 경우 캐시 클래스에 템플릿 매개 변수입니다.|  
|[CThreadPool 클래스](../atl/reference/cthreadpool-class.md)|이 클래스는 작업 항목의 큐를 처리 하는 작업자 스레드 풀을 제공 합니다.|  
|[CUrl 클래스](../atl/reference/curl-class.md)|이 클래스는 URL을 나타냅니다. 기존 URL을 구문 분석 하는지 여부를 개별적으로 URL의 각 요소를 조작할 수 있습니다 문자열 또는 처음부터 문자열을 작성 합니다.|  
|[CWorkerThread 클래스](../atl/reference/cworkerthread-class.md)|이 클래스에서 작업자 스레드 또는 기존을 사용 하 여, 하나 이상의 커널 개체 핸들을 대기 만들고 핸들 중 하나에 신호가 전달 될 때 지정 된 클라이언트 함수를 실행 합니다.|  
  
### <a name="typedefs"></a>형식 정의  
  
|||  
|-|-|  
|[CPath](../atl/reference/atl-typedefs.md#cpath)|특수화 [CPathT](../atl/reference/cpatht-class.md) 를 사용 하 여 `CString`합니다.|  
|[CPathA](../atl/reference/atl-typedefs.md#cpatha)|특수화 [CPathT](../atl/reference/cpatht-class.md) 를 사용 하 여 `CStringA`합니다.|  
|[CPathW](../atl/reference/atl-typedefs.md#cpathw)|특수화 [CPathT](../atl/reference/cpatht-class.md) 를 사용 하 여 `CStringW`합니다.|  
|[ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port)|사용 되는 형식을 [CUrl](../atl/reference/curl-class.md) 포트 번호를 지정 하는 데 있습니다.|  
  
### <a name="enums"></a>열거형  
  
|||  
|-|-|  
|[ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md)|이 열거형의 멤버에서 인식 된 스키마에 대 한 상수를 제공 [CUrl](../atl/reference/curl-class.md)합니다.|  
  
### <a name="functions"></a>함수  
  
|||  
|-|-|  
|[AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl)|안전하지 않은 문자와 공백을 이스케이프 시퀀스로 변환하는 등 URL을 정식화하려면 이 함수를 호출합니다.|  
|[AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl)|기본 URL과 상대 URL을 단일 정규 URL로 결합하려면 이 함수를 호출합니다.|  
|[AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl)|모든 안전하지 않은 문자를 이스케이프 시퀀스로 변환하려면 이 함수를 호출합니다.|  
|[AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport)|특정 인터넷 프로토콜 또는 체계와 관련 된 기본 포트 번호를 가져오려면이 함수를 호출 합니다.|  
|[AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue)|16진수의 숫자 값을 가져오려면 이 함수를 호출합니다.|  
|[AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar)|URL에서 문자를 안전하게 사용할 수 있는지 확인하려면 이 함수를 호출합니다.|  
|[AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl)|이스케이프된 문자를 원래 값으로 다시 변환하려면 이 함수를 호출합니다.|  
|[SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate)|시스템 시간을 HTTP 헤더에서 사용하기에 적합한 형식의 문자열로 변환하려면 이 함수를 호출합니다.|  

|[ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash)| 이 함수는 오버 로드 된 래퍼입니다 [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561). |  
|[ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension)| 이 함수는 오버 로드 된 래퍼입니다 [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563). |  
|[ATLPath::Append](../atl/reference/atl-path-functions.md#append)| 이 함수는 오버 로드 된 래퍼입니다 [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565). |  
|[ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot)| 이 함수는 오버 로드 된 래퍼입니다 [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567). |  
|[ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize)| 이 함수는 오버 로드 된 래퍼입니다 [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569). |  
|[ATLPath::Combine](../atl/reference/atl-path-functions.md#combine)| 이 함수는 오버 로드 된 래퍼입니다 [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571). |  
|[ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix)| 이 함수는 오버 로드 된 래퍼입니다 [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574). |  
|[ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath)| 이 함수는 오버 로드 된 래퍼입니다 [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575). |  
|[ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex)| 이 함수는 오버 로드 된 래퍼입니다 [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578). |  
|[ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists)| 이 함수는 오버 로드 된 래퍼입니다 [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584). |  
|[ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension)| 이 함수는 오버 로드 된 래퍼입니다 [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587). |  
|[ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename)| 이 함수는 오버 로드 된 래퍼입니다 [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589). |  
|[ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber)| 이 함수는 오버 로드 된 래퍼입니다 [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612). |  
|[ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory)| 이 함수는 오버 로드 된 래퍼입니다 [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621). |  
|[ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec)| 이 함수는 오버 로드 된 래퍼입니다 [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627). |  
|[ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix)| 이 함수는 오버 로드 된 래퍼입니다 [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650). |  
|[ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative)| 이 함수는 오버 로드 된 래퍼입니다 [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660). |  
|[ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot)| 이 함수는 오버 로드 된 래퍼입니다 [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674). |  
|[ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot)| 이 함수는 오버 로드 된 래퍼입니다 [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687). |  
|[ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc)| 이 함수는 오버 로드 된 래퍼입니다 [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712). |  
|[ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver)| 이 함수는 오버 로드 된 래퍼입니다 [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722). |  
|[ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare)| 이 함수는 오버 로드 된 래퍼입니다 [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723). |  
|[ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty)| 이 함수는 오버 로드 된 래퍼입니다 [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725). |  
|[ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec)| 이 함수는 오버 로드 된 래퍼입니다 [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727). |  
|[ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces)| 이 함수는 오버 로드 된 래퍼입니다 [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739). |  
|[ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto)| 이 함수는 오버 로드 된 래퍼입니다 [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740). |  
|[ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs)| 이 함수는 오버 로드 된 래퍼입니다 [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742). |  
|[ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash)| 이 함수는 오버 로드 된 래퍼입니다 [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743). |  
|[ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks)| 이 함수는 오버 로드 된 래퍼입니다 [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745). |  
|[ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension)| 이 함수는 오버 로드 된 래퍼입니다 [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746). |  
|[ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec)| 이 함수는 오버 로드 된 래퍼입니다 [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748). |  
|[ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension)| 이 함수는 오버 로드 된 래퍼입니다 [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749). |  
|[ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot)| 이 함수는 오버 로드 된 래퍼입니다 [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754). |  
|[ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath)| 이 함수는 오버 로드 된 래퍼입니다 [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756). |  
|[ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot)| 이 함수는 오버 로드 된 래퍼입니다 [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757). |  
|[ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces)| 이 함수는 오버 로드 된 래퍼입니다 [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763). |  
  

## <a name="see-also"></a>참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)   
 [ATL COM 데스크톱 구성 요소](../atl/atl-com-desktop-components.md)
