---
title: "기존 ActiveX 컨트롤 업그레이드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], Internet
- LPK files for Internet controls
- safe for scripting and initialization (controls)
- OLE controls [MFC], upgrading to ActiveX
- CAB files, for ActiveX controls
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], packaging code for download
- upgrading ActiveX controls
- licensing ActiveX controls
ms.assetid: 4d12ddfa-b491-4f9f-a0b7-b51458e05651
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a7b9c76ffd4366522dce366a165698bd3a26173
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="upgrading-an-existing-activex-control"></a>기존 ActiveX 컨트롤 업그레이드
기존 ActiveX 컨트롤 (이전의 OLE 컨트롤)를 수정 하지 않고 인터넷에서 사용할 수 있습니다. 그러나 다음 성능 향상을 위해 컨트롤을 수정 하는 것이 좋습니다. 웹 페이지에 컨트롤을 사용할 경우 추가 고려 사항 사항이 있습니다. .Ocx 파일 및 모든 지원 파일이 대상 컴퓨터에 있어야 하거나 인터넷을 통해 다운로드 합니다. 이렇게 하면 코드 크기와 다운로드 시간이 중요 한 고려 합니다. 다운로드 한 서명 된.cab 파일에 패키징할 수 있습니다. 스크립트 및 초기화에 안전으로 컨트롤을 표시할 수 있습니다.  
  
 이 문서에서는 다음 내용을 다룹니다.  
  
- [다운로드 패키징 코드](#_core_packaging_code_for_downloading)  
  
- [스크립팅과 초기화에 대 한 안전한 컨트롤 표시](#_core_marking_a_control_safe_for_scripting_and_initializing)  
  
- [라이선스 문제](#_core_licensing_issues)  
  
- [코드 서명](#_core_signing_code)  
  
- [색상표를 관리합니다.](#_core_managing_the_palette)  
  
- [Internet Explorer 브라우저 보안 수준 및 동작을 제어](#_core_internet_explorer_browser_safety_levels_and_control_behavior)  
  
 에 설명 된 대로 최적화를 추가할 수도 있습니다 [ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)합니다. 모니커를 사용 하 여 속성을 다운로드할 수 있습니다 및 대형 Blob에 설명 된 대로 비동기적으로 [인터넷의 ActiveX 컨트롤](../mfc/activex-controls-on-the-internet.md)합니다.  
  
##  <a name="_core_packaging_code_for_downloading"></a>다운로드 패키징 코드  
 이 주제에 대 한 자세한 내용은 기술 자료 문서 "패키징 MFC 컨트롤에 대 한 사용을 통해" 인터넷 (Q167158)을 참조 하십시오. 기술 자료 문서를 찾을 수 [http://support.microsoft.com/support](http://support.microsoft.com/support)합니다.  
  
### <a name="the-codebase-tag"></a>코드 베이스 태그  
 ActiveX 컨트롤 사용 하 여 웹 페이지에 포함 됩니다는 `<OBJECT>` 태그입니다. `CODEBASE` 의 매개 변수는 `<OBJECT>` 태그 컨트롤을 다운로드할 원본 위치를 지정 합니다. `CODEBASE`가리킬 수 많은 다른 파일 형식에 성공적으로 합니다.  
  
### <a name="using-the-codebase-tag-with-an-ocx-file"></a>CODEBASE 태그를 사용 하 여 OCX 파일  
  
```  
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"  
```  
  
 이 솔루션만 컨트롤의.ocx 파일을 다운로드 하 고 모든 지원 Dll 클라이언트 컴퓨터에 이미 설치 되어 있어야 합니다. 이 기능은 Internet Explorer Visual c + + 컨트롤에 대 한 지원 Dll에 제공 하기 때문에 Visual c + +를 사용 하 여 빌드한 Internet Explorer 및 MFC ActiveX 컨트롤에 대 한 작동 됩니다. Activex 컨트롤을 사용할 수 있는 또 다른 인터넷 브라우저를 사용 하 여이 컨트롤을 볼 수를이 솔루션이 작동 하지 않습니다.  
  
### <a name="using-the-codebase-tag-with-an-inf-file"></a>INF 파일을 가진 CODEBASE 태그를 사용 하 여  
  
```  
CODEBASE="http://example.microsoft.com/trustme.inf"  
```  
  
 .Ocx와 해당 지원 파일 설치.inf 파일을 제어 합니다. .Inf 파일에 서명 하는 것이 불가능 하기 때문에이 방법은 권장 되지 않습니다 (참조 [코드 서명](#_core_signing_code) 코드 서명에 대 한 포인터에 대 한).  
  
### <a name="using-the-codebase-tag-with-a-cab-file"></a>캐비닛 파일에 코드 베이스가 태그를 사용 하 여  
  
```  
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"  
```  
  
 캐비닛 파일은 MFC를 사용 하는 패키지 ActiveX 컨트롤에는 권장된 방법입니다. 캐비닛 파일에 MFC ActiveX 컨트롤을 패키징.inf 파일을 ActiveX 컨트롤 및 모든 종속 Dll (예: MFC Dll)의 컨트롤 설치에 포함 될 수 있습니다. CAB 파일을 자동으로 사용 하는 더 빠르게 다운로드할에 대 한 코드를 압축 합니다. 구성 요소 다운로드에 대 한.cab 파일을 사용할 경우 개별 구성 요소 보다 전체.cab 파일에 서명 하는 것이 더 빠릅니다.  
  
### <a name="creating-cab-files"></a>CAB 파일 만들기  
 기술 자료 문서에서 캐비닛 개발 키트를 다운로드할 수 있습니다 [310618: Microsoft 캐비닛 소프트웨어 개발 키트](http://go.microsoft.com/fwlink/p/?linkid=148204)합니다. 이 키트에 캐비닛 파일을 생성 하는 데 필요한 도구를 찾을 수 있습니다.  
  
 캐비닛 파일에서 가리키는 `CODEBASE` ActiveX 컨트롤에 대 한.ocx 파일 및.inf 파일의 설치를 제어할 수 있어야 합니다. 제어 파일의 이름을 지정 하 여 캐비닛 파일 및.inf 파일 만듭니다. 이 캐비닛 파일에 시스템에 이미 있을 수 있는 종속 Dll을 포함 하지 마십시오. 예를 들어, MFC Dll 별도 캐비닛 파일에 패키지 되 고 제어.inf 파일에서 참조 합니다.  
  
 CAB 파일을 만드는 방법에 대 한 자세한 내용은 참조 하십시오. [CAB 파일을 만드는](http://msdn.microsoft.com/en-us/cc52fd09-bdf6-4410-a693-149a308f36a3)합니다.  
  
### <a name="the-inf-file"></a>INF 파일  
 다음 예에서는, spindial.inf, 목록 지원 파일 및 버전 정보 필요한 MFC Spindial를 제어 합니다. MFC Dll의 위치는 Microsoft 웹 사이트를 확인 합니다. mfc42.cab 제공 되 고 Microsoft에서 서명 됩니다.  
  
```  
Contents of spindial.inf:  
[mfc42installer]   
file-win32-x86=http://activex.microsoft.com/controls/vc/mfc42.cab   
[Olepro32.dll] - FileVersion=5,
    0,
    4261,
    0  
[Mfc42.dll] - FileVersion=6,
    0,
    8168,
    0  
[Msvcrt.dll] - FileVersion=6,
    0,
    8168,
    0  
```  
  
### <a name="the-object-tag"></a>\<개체 > 태그  
 다음 예제를 사용 하는 `<OBJECT>` MFC Spindial 샘플 컨트롤을 패키지 하는 태그입니다.  
  
```  
<OBJECT ID="Spindial1" WIDTH=100 HEIGHT=51  
    CLASSID="CLSID:06889605-B8D0-101A-91F1-00608CEAD5B3" 
    CODEBASE="http://example.microsoft.com/spindial.cab#Version=1,0,0,001"> 
 <PARAM NAME="_Version" VALUE="65536">  
 <PARAM NAME="_ExtentX" VALUE="2646">  
 <PARAM NAME="_ExtentY" VALUE="1323">  
 <PARAM NAME="_StockProps" VALUE="0">  
 <PARAM NAME="NeedlePosition" VALUE="2">  
</OBJECT>  
```  
  
 이 경우 두 개의 파일과 spindial.ocx spindial.inf spindial.cab 포함 됩니다. 다음 명령은 캐비닛 파일을 빌드합니다.  
  
```  
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf   
```  
  
 `-s 6144` 매개 변수를 코드 서명에 캐비닛에 공간을 예약 합니다.  
  
### <a name="the-version-tag"></a>버전 태그  
 `#Version` 캐비닛 파일에 지정 된 정보로 지정 된 컨트롤에 적용 됩니다.는 `CLASSID` 의 매개 변수는 `<OBJECT>` 태그입니다.  
  
 지정 된 버전에 따라 컨트롤을 다운로드를 할 수 있습니다. 전체 사양에 대해서는 `OBJECT` 태그를 포함 하 여는 `CODEBASE` 매개 변수, 참조는 W3C 참조 합니다.  
  
##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a>스크립팅과 초기화에 대 한 안전한 컨트롤 표시  
 웹 페이지에서 사용 하는 ActiveX 컨트롤은 실제로 안전한 경우 초기화에 안전 하 고 스크립팅 작업에 안전으로 표시 되어야 합니다. 안전 컨트롤 디스크 IO를 수행 되거나 메모리 또는 컴퓨터의 레지스터에 직접 액세스 되지 않습니다.  
  
 스크립트 및 레지스트리를 통해 초기화에 안전으로 컨트롤을 표시할 수 있습니다. 수정 `DllRegisterServer` 스크립팅과 레지스트리에 지 속성에 대 한 안전한 것으로 컨트롤을 표시 하려면 다음과 유사한 항목을 추가 합니다. 다른 방법을 구현 하는 것 `IObjectSafety`합니다.  
  
 스크립트 사용 및 지 속성에 대 한 안전 표시 하 여 컨트롤에 대 한 Guid (Globally Unique Identifier)를 정의 합니다. 안전 하 게 스크립팅할 수 있는 컨트롤에는 다음과 같이 레지스트리 항목이 포함 됩니다.  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 지속적 데이터에서 안전 하 게 초기화할 수 있는 컨트롤 안전 비슷한 레지스트리 항목으로 지 속성에 표시 됩니다.  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 다음과 유사한 항목을 추가 (대체 컨트롤의 클래스 ID 대신 `{06889605-B8D0-101A-91F1-00608CEAD5B3}`) 다음 클래스 ID와 키를 연결 하려면:  
  
```  
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}   
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}   
```  
  
##  <a name="_core_licensing_issues"></a>라이선스 문제  
 웹 페이지에 라이센스가 있는 컨트롤을 사용 하려는 경우 사용권 계약을 인터넷에서 사용할 수 있습니다 및에 대 한 라이선스 패키지 파일 (LPK) 만들기를 확인 해야 합니다.  
  
 허가 된 ActiveX 컨트롤이 Internet Explorer를 실행 하는 컴퓨터 컨트롤을 사용 하도록 라이선스가 없는 경우 HTML 페이지에 제대로 로드 되지 않습니다. 예를 들어 라이센스가 있는 컨트롤으로 빌드된 경우 Visual c + +를 사용 하 여 컨트롤을 사용 하 여 HTML 페이지에서는 올바르게 로드 컴퓨터 여기서 컨트롤 작성 되지만 라이선스 정보를 제공 하지 않으면 다른 컴퓨터에 로드 되지 것입니다.  
  
 Internet Explorer에서 사용이 허가 된 ActiveX 컨트롤을 사용 하려면 컨트롤에 대 한 라이선스 수 있는지 확인 하려면 공급 업체의 사용권 계약을 확인 해야 합니다.  
  
-   재배포  
  
-   인터넷에서 컨트롤 사용  
  
-   코드 베이스 매개 변수 사용  
  
 라이센스가 없는 컴퓨터에 HTML 페이지에 라이센스가 있는 컨트롤을 사용 하려면 라이선스 패키지 파일 (LPK)를 생성 해야 합니다. LPK 파일 HTML 페이지의 사용이 허가 된 컨트롤에 대 한 런타임 라이선스를 포함합니다. 이 파일은 LPK_TOOL를 통해 생성 됩니다. ActiveX SDK와 함께 제공 되는 EXE 합니다. 자세한 내용은 MSDN 웹 사이트를 참조 하십시오. [http://msdn.microsoft.com](http://msdn.microsoft.com)합니다.  
  
#### <a name="to-create-an-lpk-file"></a>LPK 파일을 만들려면  
  
1.  LPK_TOOL를 실행 합니다. 라이선스를 체결 컨트롤을 사용 하는 컴퓨터에 대 한 EXE 합니다.  
  
2.  에 **라이선스 패키지 작성 도구** 대화 상자는 **사용할 수 있는 컨트롤** 목록 상자에서 각 선택 하는 HTML 페이지에 사용 되 고 클릭 하 여 ActiveX 컨트롤 사용이 허가 **추가**.  
  
3.  클릭 **저장 후 종료** LPK 파일에 대 한 이름을 입력 합니다. LPK 파일 만들고 응용 프로그램을 닫습니다.  
  
#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>HTML 페이지에 라이센스가 있는 컨트롤을 포함 하려면  
  
1.  HTML 페이지를 편집 합니다. HTML 페이지에 삽입 한 \<개체 > 다른 하기 전에 라이선스 관리자 개체에 대 한 태그 \<개체 > 태그입니다. 라이선스 관리자에는 Internet Explorer과 함께 설치 된 ActiveX 컨트롤입니다. 컨트롤의 클래스 ID는 다음과 같습니다. LPK 파일의 이름과 경로를 라이선스 관리자 개체의 LPKPath 속성을 설정 합니다. HTML 페이지 당 LPK 파일 하나만 있을 수 있습니다.  
  
 ```  
 <OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
 <PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">  
 </OBJECT>  
 ```  
  
2.  삽입 된 \<개체 > 라이선스 관리자 태그 뒤에 라이센스가 있는 컨트롤에 대 한 태그입니다.  
  
     예를 들어 Microsoft 마스킹된 편집 컨트롤을 표시 하는 HTML 페이지는 다음과 같습니다. ID는 라이선스 관리자 컨트롤에 대 한 첫 번째 클래스, 마스킹된 편집 컨트롤에 대 한 ID가 두 번째 클래스입니다. 앞에서 만든 제작 파일의 상대 경로를 가리키도록 태그를 변경 하 고 컨트롤의 클래스 ID를 포함 하 여 개체 태그를 추가 합니다.  
  
3.  삽입 된 \<EMBED > NCompass ActiveX 플러그 인을 사용 하는 경우 LPK 파일에 대 한 특성입니다.  
  
     다른 컨트롤을 볼 수 있는 경우 활성 지원 브라우저-NCompass ActiveX 플러그 인을 사용 하 여 Netscape 예를 들어-추가 해야 합니다는 \<EMBED > 아래와 같이 구문입니다.  
  
 ```  
 <OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
 <PARAM NAME="LPKPath" VALUE="maskedit.lpk">  
 
 <EMBED SRC = "maskedit.LPK">  
 
 </OBJECT>  
 <OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>  
 </OBJECT>  
 ```  
  
 컨트롤 라이선스에 대 한 자세한 내용은 참조 [ActiveX 컨트롤: ActiveX 컨트롤 라이선스](../mfc/mfc-activex-controls-licensing-an-activex-control.md)합니다.  
  
##  <a name="_core_signing_code"></a>코드 서명  
 코드의 소스를 식별 하도록 설계 된 코드 서명 및 서명 된 이후 코드가 변경 되지 않은 되도록 합니다. 브라우저의 보안 설정에 따라 사용자가 코드를 다운로드 하기 전에 경고가 표시 될 수 있습니다. 사용자가 특정 인증서 소유자 또는는 case 코드에는 이들 서명한 신뢰할 수 있는 경고 없이 다운로드 됩니다 회사를 신뢰 하도록 선택할 수 있습니다. 코드 변조를 방지 하기 위해 디지털로 서명 됩니다.  
  
 최종 코드 신뢰 경고 메시지를 표시 하지 않고 컨트롤을 자동으로 다운로드 될 수 있도록 서명 되어 있는지 확인 합니다. 에 코드 서명 하는 방법에 대 한 내용은 Authenticode ActiveX SDK에 관한 설명서를 확인 하 고 참조 [CAB 파일 서명](http://msdn.microsoft.com/en-us/04d8b47a-8f1c-4b54-ab90-730fcdc03747)합니다.  
  
 신뢰 및 브라우저 보안 수준 설정에 따라 서명 한 사용자나 회사를 식별 하는 인증서를 표시할 수 있습니다. 보안 수준이 none, 또는 서명 된 컨트롤의 인증서 소유자 신뢰할 수 있는 경우 인증서 표시 되지 않습니다. 참조 [Internet Explorer 브라우저 보안 수준 및 동작을 제어](#_core_internet_explorer_browser_safety_levels_and_control_behavior) 컨트롤이 다운로드 되는 여부 및 표시 된 인증서는 브라우저 보안 설정 됩니다 결정 하는 방법에 대 한 내용은 합니다.  
  
 디지털 서명 보장 코드 서명 된 이후 변경 되지 않았습니다. 해시 코드를 가져오고 인증서에 포함 됩니다. 이 해시는 나중에 수행할 다운로드 되는 코드를 실행 하기 전에 코드의 해시와 비교 됩니다. Verisign과 같은 회사 코드 서명 하는 데 필요한 개인 및 공개 키를 제공할 수 있습니다. ActiveX SDK MakeCert, 테스트 인증서를 만들기 위한 유틸리티 함께 제공 됩니다.  
  
##  <a name="_core_managing_the_palette"></a>색상표를 관리합니다.  
 색상표를 결정 하 고 앰비언트 속성으로 사용할 수 있도록 하는 컨테이너 **DISPID_AMBIENT_PALETTE**합니다. 컨테이너 (예를 들어 Internet Explorer) 자신의 색상표를 결정 하는 페이지에서 모든 ActiveX 컨트롤에서 사용 되는 색상표를 선택 합니다. 이 디스플레이 깜박이 것을 금지 하 고 일관 된 모양을 제공 합니다.  
  
 컨트롤 `OnAmbientPropertyChange` 팔레트에 대 한 변경 알림을 처리 하도록 합니다.  
  
 컨트롤 `OnGetColorSet` 반환할 색 색상표를 그릴로 설정 합니다. 컨테이너는 컨트롤 팔레트 인식 인지 확인 하려면 반환 값을 사용 합니다.  
  
 OCX 96 지침에서 컨트롤은 백그라운드에서에서 팔레트를 나타내려고 항상 있어야 합니다.  
  
 앰비언트 palette 속성을 사용 하지 않는 오래 된 컨테이너 송신할 `WM_QUERYNEWPALETTE` 및 `WM_PALETTECHANGED` 메시지입니다. 컨트롤 `OnQueryNewPalette` 및 `OnPaletteChanged` 이러한 메시지를 처리 합니다.  
  
##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a>Internet Explorer 브라우저 보안 수준 및 동작을 제어  
 브라우저에 사용자가 구성 가능한 보안 수준에 대 한 옵션이 있습니다. 웹 페이지는 사용자의 컴퓨터를 손상 시킬 수 있는 액티브 콘텐츠를 포함할 수 있으므로 브라우저 보안 수준에 대 한 옵션을 선택할 수 있습니다. 에 브라우저 보안 수준을 구현 하는 방식에 따라 컨트롤 전혀 다운로드 되지 또는 인증서 또는 사용자 컨트롤을 다운로드할 지 여부를 런타임에 선택할 수 있도록 경고 메시지가 표시 됩니다. 높음, 보통 및 낮은 보안 수준에서 Internet Explorer에서 ActiveX 컨트롤의 동작과 다음과 같습니다.  
  
### <a name="high-safety-mode"></a>보호 우선 모드  
  
-   서명 되지 않은 컨트롤을 다운로드 하지 않습니다.  
  
-   신뢰할 수 없는 경우 서명 된 컨트롤은 인증서가 표시 됩니다 (사용자는 이제이 인증서 소유자의 코드를 항상 신뢰할 수 있는 옵션이 선택 가능).  
  
-   안전한 것으로 표시 된 컨트롤에만 영구 데이터 및 스크립팅할 수 있습니다.  
  
### <a name="medium-safety-mode"></a>보통 보안 모드  
  
-   서명 되지 않은 컨트롤을 다운로드 하기 전에 경고가 표시 됩니다.  
  
-   신뢰할 수 없는 경우 서명 된 컨트롤은 인증서가 표시 됩니다.  
  
-   안전한 것으로 표시 되지 않은 컨트롤 경고가 표시 됩니다.  
  
### <a name="low-safety-mode"></a>낮은 보호 우선 모드  
  
-   경고 없이 컨트롤을 다운로드 합니다.  
  
-   스크립트와 지 속성이 경고 없이 발생합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)   
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)   
 [MFC ActiveX 컨트롤: ActiveX 컨트롤 라이선스](../mfc/mfc-activex-controls-licensing-an-activex-control.md)

