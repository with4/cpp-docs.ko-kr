---
title: "링커 도구 오류 LNK1168 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1168"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1168"
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1168
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

filename을\(를\) 쓰기용으로 열 수 없습니다.  
  
 링커는 `filename`에 쓸 수 없습니다.  파일이 사용 중이고 파일 핸들이 다른 프로세스에 의해 잠겨 있거나, 파일 또는 파일이 있는 디렉터리나 네트워크 공유에 대한 쓰기 권한이 없을 수 있습니다.  이 오류는 바이러스 백신 프로그램이 보유한 잠금, 파일 검색 인덱싱 프로세스 또는 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 빌드 시스템이 보유한 잠금 해제 지연 등 일시적인 조건으로 인해 발생하는 경우가 많습니다.  
  
 이 문제를 해결하려면 `filename` 파일 핸들이 잠겨 있지 않은지, 파일에 대해 쓰기 권한이 있는지 확인합니다.  실행 파일이라면 이미 실행 중이 아닌지 확인합니다.  
  
 Windows SysInternals 유틸리티 [핸들](http://technet.microsoft.com/sysinternals/bb896655.aspx) 또는 [프로세스 탐색기](http://technet.microsoft.com/sysinternals/bb896653)를 사용하여 어떤 프로세스에 `filename`에 대한 파일 핸들 잠금이 있는지 확인합니다.  프로세스 탐색기를 사용하여 열린 파일 핸들에 대한 잠금을 해제할 수도 있습니다.  이러한 유틸리티를 사용하는 방법에 대한 자세한 내용은 함께 제공된 도움말 파일을 참조하세요.  
  
 파일이 바이러스 백신 프로그램으로 잠겨 있으면 백신 프로그램의 자동 검색에서 빌드 출력 디렉터리를 제외하여 이 문제를 해결할 수 있습니다.  바이러스 검색 프로그램은 종종 파일 시스템에서 새 파일 생성에 의해 트리거되며 검색이 진행되는 동안 파일에 대해 잠금을 설정합니다.  검색에서 특정 디렉터리를 제외하는 방법에 대한 자세한 내용은 바이러스 백신 프로그램 설명서를 참조하세요.  
  
 파일이 검색 인덱싱 서비스에 의해 잠겨 있으면 자동 인덱싱에서 빌드 출력 디렉터리를 제외하여 이 문제를 해결할 수 있습니다.  자세한 내용은 인덱싱 서비스의 설명서를 참조하세요.  Windows 검색 인덱싱 서비스를 변경하려면 Windows **제어판**의 **인덱싱 옵션**을 사용합니다.  자세한 내용은 [색인을 사용하여 Windows 검색 기능 향상: 질문과 대답](http://windows.microsoft.com/en-us/windows/improve-windows-searches-using-index-faq#1TC=windows-7)을 참조하세요.  
  
 실행 파일을 빌드 프로세스에 의해 덮어쓸 수 없는 경우 파일 탐색기에 의해 잠겨 있을 수 있습니다.  **응용 프로그램 환경** 서비스를 사용할 수 없는 경우 파일 탐색기가 장시간 동안 실행 파일 핸들 잠금을 유지할 수 있습니다.  이 문제를 해결하려면 **services.msc**를 실행한 다음 **응용 프로그램 환경** 서비스의 **속성** 대화 상자를 엽니다.  **시작 유형**을 **사용 안 함**에서 **수동**으로 변경합니다.  
  
## 참고 항목  
 [Visual C\+\+에서 솔루션 또는 ActiveX 프로젝트를 빌드하려고 할 때 "오류 PRJ0008" 또는 "심각한 오류 LNK1168" 오류 메시지가 발생할 수 있습니다.](http://support.microsoft.com/kb/308358)