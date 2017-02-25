---
title: "디자인 타임에 컨트롤 속성 설정 | Microsoft Docs"
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
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], 속성"
ms.assetid: 963bf498-d371-4cfd-8bed-865427dcfad9
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 디자인 타임에 컨트롤 속성 설정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

대화 상자 편집기를 사용하여 디자인 타임에 컨트롤의 속성을 설정할 수 있습니다.  속성을 설정하면 리소스 편집기가 지정된 값으로 컨트롤을 초기화합니다.  초기화한 후에도 속성은 프로그래밍 방식으로 변경할 수 있습니다.  
  
 [데이터 바인딩된 컨트롤](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)에 있는 **DataSource** 속성을 사용하여 바인딩할 [데이터 소스](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md) 컨트롤을 지정할 수 있습니다.  
  
 단순 바인딩 ADO 데이터 바인딩 컨트롤을 ADO 데이터 컨트롤\(ADODC\)로 바인딩할 때는 **DataField** 속성을 행 집합의 유효한 필드로 설정하여 컨트롤을 열과 연결해야 합니다.  그렇지 않으면 컴파일된 응용 프로그램은 실행 중인 디버그 빌드에서 어설션합니다. 어설션은 컨트롤이 Null 열에 바인딩되었음을 단순히 표시하기만 합니다.  
  
> [!NOTE]
>  **일반** 속성 탭에서 컨트롤 식별자와 .rc 파일에 필요한 다른 속성을 지정할 수 있습니다. .rc 파일은 나중에 컴파일되어 Windows 프로그램 리소스 코드를 생성합니다.  
  
### 모두 탭에서 속성을 설정하려면  
  
1.  대화 상자에 [ActiveX 컨트롤을 삽입](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md)합니다.  
  
2.  마우스 오른쪽 단추로 대화 상자 편집기의 컨트롤을 클릭한 다음 **속성**을 클릭합니다.  
  
3.  **모두** 탭을 클릭하여 컨트롤의 속성을 표시합니다.  주어진 속성에 대해 초기화 값을 입력합니다.  
  
 런타임에 컨트롤 속성을 설정하려면 [컨트롤의 런타임 동작 수정](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)을 참조하십시오.  
  
## 참고 항목  
 [ActiveX 컨트롤 사용](../../data/ado-rdo/using-activex-controls.md)