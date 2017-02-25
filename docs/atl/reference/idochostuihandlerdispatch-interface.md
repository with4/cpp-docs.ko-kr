---
title: "IDocHostUIHandlerDispatch Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDocHostUIHandlerDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDocHostUIHandlerDispatch interface"
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IDocHostUIHandlerDispatch Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft HTML 구문 분석 및 렌더링 엔진 인터페이스.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
interface IDocHostUIHandlerDispatch : IDispatch  
  
```  
  
## Members  
  
### Public 메서드  
  
> [!NOTE]
>  입력부 SDK 참조 항목의 멤버에 대해 다음 표에 있는 링크를에서 하려고는  [IDocUIHostHandler](https://msdn.microsoft.com/en-us/library/aa753260.aspx) 인터페이스.  `IDocHostUIHandlerDispatch`같은 기능으로  **IDocUIHostHandler**와 차이 `IDocHostUIHandlerDispatch` 이지만 dispinterface는  **IDocUIHostHandler** 사용자 지정 하는 인터페이스입니다.  
  
|||  
|-|-|  
|[\<caps:sentence id\="tgt7" sentenceid\="bbafd0070a97938421603b1ef8409510" class\="tgtSentence"\>EnableModeless\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753253.aspx)|MSHTML 구현에서 호출  [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115).  MSHTML 모달 UI를 표시 하는 경우에 호출 됩니다.|  
|[\<caps:sentence id\="tgt10" sentenceid\="2cfbfb70fe0af79263134b694d06311c" class\="tgtSentence"\>FilterDataObject\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753254.aspx)|MSHTML MSHTML의 데이터 개체를 바꿀 수 있는 호스트를 허용 하 여 호스트에서 호출 됩니다.|  
|[\<caps:sentence id\="tgt12" sentenceid\="715255e2d7f611c97308a373328e19a0" class\="tgtSentence"\>GetDropTarget\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753255.aspx)|놓기 대상으로 호스트가 제공 하는 대신 사용 하면 MSHTML에서 호출  [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[\<caps:sentence id\="tgt14" sentenceid\="5a51a8633a0d2036f843073d6f35a4af" class\="tgtSentence"\>GetExternal\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753256.aspx)|호스트의 IDispatch 인터페이스를 가져오려면 MSHTML에 의해 호출 됩니다.|  
|[\<caps:sentence id\="tgt16" sentenceid\="ce27e0c2f7ebb0aaa2f9088818dc8347" class\="tgtSentence"\>GetHostInfo\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753257.aspx)|MSHTML 호스트의 UI 기능을 검색합니다.|  
|[\<caps:sentence id\="tgt18" sentenceid\="693bd2149b17c4586cdc167e13e59f0a" class\="tgtSentence"\>GetOptionKeyPath\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753258.aspx)|MSHTML에서 사용자 기본 설정을 저장 하는 레지스트리 키를 반환 합니다.|  
|[\<caps:sentence id\="tgt20" sentenceid\="7fce94585b477684cc21a38fe9ee288c" class\="tgtSentence"\>HideUI\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753259.aspx)|MSHTML의 메뉴 및 도구 모음을 제거할 때 호출 됩니다.|  
|[\<caps:sentence id\="tgt22" sentenceid\="359e4dcbd80b962decf88ef02d66fe14" class\="tgtSentence"\>OnDocWindowActivate\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753261.aspx)|MSHTML 구현에서 호출  [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281).|  
|[\<caps:sentence id\="tgt24" sentenceid\="8e472d7f3f3064d2ee6fdddd83002b86" class\="tgtSentence"\>OnFrameWindowActivate\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753262.aspx)|MSHTML 구현에서 호출  [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969).|  
|[\<caps:sentence id\="tgt26" sentenceid\="3fd38deec5e9f4201074e886bfb178a5" class\="tgtSentence"\>ResizeBorder\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753263.aspx)|MSHTML 구현에서 호출  [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053).|  
|[\<caps:sentence id\="tgt28" sentenceid\="2f382ba3de5494d18b20ccfa348f795e" class\="tgtSentence"\>ShowContextMenu\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753264.aspx)|상황에 맞는 메뉴를 표시 하려면 MSHTML에서 호출 됩니다.|  
|[\<caps:sentence id\="tgt30" sentenceid\="c6978c4c8ab30ae8380439da613bb63c" class\="tgtSentence"\>ShowUI\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753265.aspx)|호스트를 MSHTML 메뉴 및 도구 모음을 바꿀 수 있습니다.|  
|[\<caps:sentence id\="tgt32" sentenceid\="97bfd5aead25a2d9870b38da4b6745cd" class\="tgtSentence"\>TranslateAccelerator\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753266.aspx)|MSHTML에서 호출할 때  [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) 또는  [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) 라고 합니다.|  
|[\<caps:sentence id\="tgt34" sentenceid\="55c20a6fb6b05f6059d72b2854a7d7e2" class\="tgtSentence"\>TranslateUrl\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753267.aspx)|호스트 로드 하는 URL을 수정할 수 있도록 MSHTML에 의해 호출 됩니다.|  
|[\<caps:sentence id\="tgt36" sentenceid\="8fdf7c2c3ebf5fa12ecc909279c951ff" class\="tgtSentence"\>Updateui 라고\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753268.aspx)|명령 상태가 변경 되었음을 호스트에 알립니다.|  
  
## 설명  
 호스트가 메뉴, 도구 모음 및 Microsoft HTML 구문 분석 및 렌더링 엔진 \(MSHTML\)에서이 인터페이스를 구현 하 여 사용 하는 상황에 맞는 메뉴를 바꿀 수 있습니다.  
  
## 요구 사항  
 이 인터페이스의 정의 아래와 같이 C\+\+, IDL로 사용할입니다.  
  
|형식 정의|파일|  
|-----------|--------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(Atlbase.h에 포함 됨\)|  
  
## 참고 항목  
 [IDocUIHostHandler](https://msdn.microsoft.com/en-us/library/aa753260.aspx)