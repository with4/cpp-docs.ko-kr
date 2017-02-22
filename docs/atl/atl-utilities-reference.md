---
title: "ATL 유틸리티 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ATL 유틸리티 참조
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL 경로 Url의 형태로 조작 하기 위한 코드를 제공  [CPathT](../atl/reference/cpatht-class.md) 및  [용지의](../atl/reference/curl-class.md).  스레드 풀에서  [CThreadPool](../atl/reference/cthreadpool-class.md), 응용 프로그램에서 사용할 수 있습니다.  이 코드는 atlpath.h 및 atlutil.h에서 찾을 수 있습니다.  
  
### 클래스  
  
|||  
|-|-|  
|[CPathT 클래스](../atl/reference/cpatht-class.md)|이 클래스는 경로 나타냅니다.|  
|[CDebugReportHook 클래스](../atl/reference/cdebugreporthook-class.md)|이 클래스를 사용 하 여 디버그 보고서를 보내려면 명명 된 파이프에.|  
|[CNonStatelessWorker 클래스](../atl/reference/cnonstatelessworker-class.md)|스레드 풀에서 요청을 받아이 만들어지고 소멸 하는 작업자 개체에 각 요청을 전달 합니다.|  
|[CNoWorkerThread 클래스](../atl/reference/cnoworkerthread-class.md)|이 클래스에 대 한 인수로 사용 된 `MonitorClass` 동적 캐시를 유지 관리 하지 않을 경우 캐시 클래스 템플릿 매개 변수.|  
|[CThreadPool 클래스](../atl/reference/cthreadpool-class.md)|이 클래스는 큐의 작업 항목을 처리 하는 작업자 스레드 풀을 제공 합니다.|  
|[CUrl 클래스](../atl/reference/curl-class.md)|이 클래스는 URL을 나타냅니다.  기존 URL을 구문 분석 하는 여부와 독립적으로 다른 URL의 각 요소를 조작할 수 있습니다 문자열 또는 문자열 처음부터 새로 작성 합니다.|  
|[CWorkerThread 클래스](../atl/reference/cworkerthread-class.md)|이 클래스 작업자 스레드를 만듭니다 또는 기존 사용, 여러 커널 개체 핸들을 대기 및 신호를 핸들 중 하나를 지정한 클라이언트 함수 실행.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[CPath](../Topic/CPath.md)|특수화를  [CPathT](../atl/reference/cpatht-class.md) 를 사용 하 여 `CString`.|  
|[CPathA](../Topic/CPathA.md)|특수화를  [CPathT](../atl/reference/cpatht-class.md) 를 사용 하 여 `CStringA`.|  
|[CPathW](../Topic/CPathW.md)|특수화를  [CPathT](../atl/reference/cpatht-class.md) 를 사용 하 여 `CStringW`.|  
|[ATL\_URL\_PORT](../Topic/ATL_URL_PORT.md)|형식을 사용 하 여  [용지의](../atl/reference/curl-class.md) 포트 번호를 지정 합니다.|  
  
### 열거형  
  
|||  
|-|-|  
|[ATL\_URL\_SCHEME](../Topic/ATL_URL_SCHEME.md)|이 열거형의 멤버 상수를 이해 하 여 구성표를 제공  [용지의](../atl/reference/curl-class.md).|  
  
### 함수  
  
|||  
|-|-|  
|[AtlCanonicalizeUrl](../Topic/AtlCanonicalizeUrl.md)|URL 이스케이프 시퀀스로 변환 하는 안전 하지 않은 문자와 공백은 포함 표준화 하려면이 함수를 호출 합니다.|  
|[AtlCombineUrl](../Topic/AtlCombineUrl.md)|한 정식에 해당 하는 URL에 기본 URL 및 상대 URL을 결합 하는이 함수를 호출 합니다.|  
|[AtlEscapeUrl](../Topic/AtlEscapeUrl.md)|모든 안전 하지 않은 문자를 이스케이프 시퀀스를 변환 하려면이 함수를 호출 합니다.|  
|[AtlGetDefaultUrlPort](../Topic/AtlGetDefaultUrlPort.md)|특정 인터넷 프로토콜 또는 구성표와 연결 된 기본 포트 번호를 가져오려면이 함수를 호출 합니다.|  
|[AtlHexValue](../Topic/AtlHexValue.md)|숫자의 16 진수 값을 가져오려면이 함수를 호출 합니다.|  
|[AtlIsUnsafeUrlChar](../Topic/AtlIsUnsafeUrlChar.md)|문자를 안전 하 게 사용할 URL에 있는지 확인 하려면이 함수를 호출 합니다.|  
|[AtlUnescapeUrl](../Topic/AtlUnescapeUrl.md)|이스케이프 된 문자를 원래 값으로 변환 하려면이 함수를 호출 합니다.|  
|[SystemTimeToHttpDate](../Topic/SystemTimeToHttpDate.md)|시스템 시간 문자열의 HTTP 헤더를 사용 하 여 적합 한 형식으로 변환 하려면이 함수를 호출 합니다.|  
|[ATLPath::AddBackslash](../Topic/ATLPath::AddBackslash.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathAddBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773561).|  
|[ATLPath::AddExtension](../Topic/ATLPath::AddExtension.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathAddExtension](http://msdn.microsoft.com/library/windows/desktop/bb773563).|  
|[ATLPath::Append](../Topic/ATLPath::Append.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathAppend](http://msdn.microsoft.com/library/windows/desktop/bb773565).|  
|[ATLPath::BuildRoot](../Topic/ATLPath::BuildRoot.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathBuildRoot](http://msdn.microsoft.com/library/windows/desktop/bb773567).|  
|[ATLPath::Canonicalize](../Topic/ATLPath::Canonicalize.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathCanonicalize](http://msdn.microsoft.com/library/windows/desktop/bb773569).|  
|[ATLPath::Combine](../Topic/ATLPath::Combine.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathCombine](http://msdn.microsoft.com/library/windows/desktop/bb773571).|  
|[ATLPath::CommonPrefix](../Topic/ATLPath::CommonPrefix.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathCommonPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773574).|  
|[ATLPath::CompactPath](../Topic/ATLPath::CompactPath.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathCompactPath](http://msdn.microsoft.com/library/windows/desktop/bb773575).|  
|[ATLPath::CompactPathEx](../Topic/ATLPath::CompactPathEx.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathCompactPathEx](http://msdn.microsoft.com/library/windows/desktop/bb773578).|  
|[ATLPath::FileExists](../Topic/ATLPath::FileExists.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathFileExists](http://msdn.microsoft.com/library/windows/desktop/bb773584).|  
|[ATLPath::FindExtension](../Topic/ATLPath::FindExtension.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathFindExtension](http://msdn.microsoft.com/library/windows/desktop/bb773587).|  
|[ATLPath::FindFileName](../Topic/ATLPath::FindFileName.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589).|  
|[ATLPath::GetDriveNumber](../Topic/ATLPath::GetDriveNumber.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathGetDriveNumber](http://msdn.microsoft.com/library/windows/desktop/bb773612).|  
|[ATLPath::IsDirectory](../Topic/ATLPath::IsDirectory.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathIsDirectory](http://msdn.microsoft.com/library/windows/desktop/bb773621).|  
|[ATLPath::IsFileSpec](../Topic/ATLPath::IsFileSpec.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathIsFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773627).|  
|[ATLPath::IsPrefix](../Topic/ATLPath::IsPrefix.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathIsPrefix](http://msdn.microsoft.com/library/windows/desktop/bb773650).|  
|[ATLPath::IsRelative](../Topic/ATLPath::IsRelative.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathIsRelative](http://msdn.microsoft.com/library/windows/desktop/bb773660).|  
|[ATLPath::IsRoot](../Topic/ATLPath::IsRoot.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathIsRoot](http://msdn.microsoft.com/library/windows/desktop/bb773674).|  
|[ATLPath::IsSameRoot](../Topic/ATLPath::IsSameRoot.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathIsSameRoot](http://msdn.microsoft.com/library/windows/desktop/bb773687).|  
|[ATLPath::IsUNC](../Topic/ATLPath::IsUNC.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathIsUNC](http://msdn.microsoft.com/library/windows/desktop/bb773712).|  
|[ATLPath::IsUNCServer](../Topic/ATLPath::IsUNCServer.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathIsUNCServer](http://msdn.microsoft.com/library/windows/desktop/bb773722).|  
|[ATLPath::IsUNCServerShare](../Topic/ATLPath::IsUNCServerShare.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathIsUNCServerShare](http://msdn.microsoft.com/library/windows/desktop/bb773723).|  
|[ATLPath::MakePretty](../Topic/ATLPath::MakePretty.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathMakePretty](http://msdn.microsoft.com/library/windows/desktop/bb773725).|  
|[ATLPath::MatchSpec](../Topic/ATLPath::MatchSpec.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathMatchSpec](http://msdn.microsoft.com/library/windows/desktop/bb773727).|  
|[ATLPath::QuoteSpaces](../Topic/ATLPath::QuoteSpaces.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathQuoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773739).|  
|[ATLPath::RelativePathTo](../Topic/ATLPath::RelativePathTo.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathRelativePathTo](http://msdn.microsoft.com/library/windows/desktop/bb773740).|  
|[ATLPath::RemoveArgs](../Topic/ATLPath::RemoveArgs.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathRemoveArgs](http://msdn.microsoft.com/library/windows/desktop/bb773742).|  
|[ATLPath::RemoveBackslash](../Topic/ATLPath::RemoveBackslash.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathRemoveBackslash](http://msdn.microsoft.com/library/windows/desktop/bb773743).|  
|[ATLPath::RemoveBlanks](../Topic/ATLPath::RemoveBlanks.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathRemoveBlanks](http://msdn.microsoft.com/library/windows/desktop/bb773745).|  
|[ATLPath::RemoveExtension](../Topic/ATLPath::RemoveExtension.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathRemoveExtension](http://msdn.microsoft.com/library/windows/desktop/bb773746).|  
|[ATLPath::RemoveFileSpec](../Topic/ATLPath::RemoveFileSpec.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathRemoveFileSpec](http://msdn.microsoft.com/library/windows/desktop/bb773748).|  
|[ATLPath::RenameExtension](../Topic/ATLPath::RenameExtension.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathRenameExtension](http://msdn.microsoft.com/library/windows/desktop/bb773749).|  
|[ATLPath::SkipRoot](../Topic/ATLPath::SkipRoot.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathSkipRoot](http://msdn.microsoft.com/library/windows/desktop/bb773754).|  
|[ATLPath::StripPath](../Topic/ATLPath::StripPath.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathStripPath](http://msdn.microsoft.com/library/windows/desktop/bb773756).|  
|[ATLPath::StripToRoot](../Topic/ATLPath::StripToRoot.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathStripToRoot](http://msdn.microsoft.com/library/windows/desktop/bb773757).|  
|[ATLPath::UnquoteSpaces](../Topic/ATLPath::UnquoteSpaces.md)|이 함수는 오버 로드 된에 대 한 래퍼입니다  [PathUnquoteSpaces](http://msdn.microsoft.com/library/windows/desktop/bb773763).|  
  
### 매크로  
  
|||  
|-|-|  
|[ATL\_URL 플래그](../Topic/ATL_URL%20Flags.md)|이러한 플래그의 동작을 수정  [AtlEscapeUrl](../Topic/AtlEscapeUrl.md) 및  [AtlCanonicalizeUrl](../Topic/AtlCanonicalizeUrl.md) .|  
|[ATL\_WORKER\_THREAD\_WAIT](../Topic/ATL_WORKER_THREAD_WAIT.md)|이 매크로 기본 값은 밀리초 단위로 정의  [CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md) 종료 하는 데 작업자 스레드를 대기 합니다.|  
|[ATLS\_DEFAULT\_THREADPOOLSHUTDOWNTIMEOUT](../Topic/ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT.md)|이 매크로 기본 시간을 밀리초 단위로 정의  [CThreadPool](../atl/reference/cthreadpool-class.md) 스레드 종료 대기 합니다.|  
|[ATLS\_DEFAULT\_THREADSPERPROC](../Topic/ATLS_DEFAULT_THREADSPERPROC.md)|이 매크로 사용 하 여 프로세서 당 스레드 수의 기본값은 정의  [CThreadPool](../atl/reference/cthreadpool-class.md).|  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)