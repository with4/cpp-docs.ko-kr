---
title: "Visual C++ ActiveX 컨트롤 재배포 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨트롤[C++], 배포"
  - "컨트롤[C++], 재배포"
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++ ActiveX 컨트롤 재배포
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 6.0에서는 응용 프로그램에서 사용한 다음 재배포할 수 있는 ActiveX 컨트롤을 제공합니다.  이러한 컨트롤은 Visual C\+\+에 더 이상 포함되지 않습니다.  사용자는 Visual C\+\+ 6.0의 사용권 계약에 따라 Visual C\+\+로 개발한 응용 프로그램과 함께 이러한 컨트롤을 다시 배포할 수 있습니다.  
  
> [!NOTE]
>  Visual C\+\+ 6.0은 더 이상 Microsoft에서 지원하지 않습니다.  
  
 재배포할 수 있는 Visual C\+\+ 6.0 ActiveX 컨트롤의 목록을 보려면 Visual C\+\+ 6.0 제품의 첫 번째 CD에서 Common\\Redist\\Redist.txt 파일을 참조하십시오.  
  
 응용 프로그램을 배포할 때는 Regsvr32.exe를 사용하여 ActiveX 컨트롤에 대한 .ocx 파일을 설치하고 등록해야 하며  대상 컴퓨터에 다음과 같은 시스템 파일의 현재 버전이 있어야 합니다. 아래 목록에서 별표가 표시된 파일은 등록해야 합니다.  
  
-   Asycfilt.dll  
  
-   Comcat.dll \*  
  
-   Oleaut32.dll \*  
  
-   Olepro32.dll \*  
  
-   Stdole2.tlb  
  
 대상 시스템에 이러한 DLL 파일이 없는 경우에는 미리 지정된 해당 운영 체제의 업데이트 메커니즘을 사용하여 DLL을 업데이트해야 합니다.  Windows 운영 체제의 최신 서비스 팩은 [http:\/\/www.update.microsoft.com\/microsoftupdate\/v6\/vistadefault.aspx?ln\=ko\-kr](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=ko-kr)에서 다운로드할 수 있습니다.  
  
 데이터베이스에 연결하는 ActiveX 컨트롤 중 하나를 응용 프로그램에서 사용하는 경우에는 대상 시스템에 MDAC\(Microsoft Data Access Components\)가 설치되어 있어야 합니다.  자세한 내용은 [데이터베이스 지원 파일 재배포](../ide/redistributing-database-support-files.md)를 참조하십시오.  
  
 또한 데이터베이스에 연결하는 ActiveX 컨트롤을 사용하는 경우에는 대상 컴퓨터에서 데이터 소스 이름을 복제해야 합니다.  `ConfigDSN`과 같은 함수를 사용하여 프로그래밍 방식으로 이 작업을 할 수 있습니다.  
  
 재배포 가능한 일부 ActiveX 컨트롤에는 추가적인 종속 파일이 있습니다.  Visual C\+\+ 6.0 제품 CD의 운영\_체제\_이름\\System 폴더에는 각 .ocx 파일에 대한 .dep 파일이 있습니다.  재배포할 각 .ocx 파일에 대해 해당 .dep 파일에서 한 개 이상의 USES 항목을 조사합니다.  파일이 나열되어 있으면 해당 파일이 대상 컴퓨터에 있는지 확인해야 합니다.  .ocx 파일을 직접 지원하는 DLL을 모두 등록해야 합니다.  Regsvr32.exe를 제대로 실행하려면 컨트롤에서 정적으로 로드하는 모든 DLL이 대상 컴퓨터에 있어야 합니다. 또한, 종속성으로 나열된 DLL에 대해서도 Visual C\+\+ 6.0 CD의 Os\\System 폴더에 해당 .dep 파일이 있으면 그 .dep 파일에서 USES 항목을 조사해야 합니다.  
  
## 참고 항목  
 [Visual C\+\+ 파일 재배포](../ide/redistributing-visual-cpp-files.md)