---
layout: post
categories: java
title: "[JavaFX] FXML 컨테이너"
tags: [JavaFX]
comments: true
---

## AnchorPane
- 좌상단(0, 0)을 기준으로 컨트롤을 배치하는 컨테이너

|태그 및 속성|설명|적용|
|---|---|---|
|prefWidth|폭을 설정|AnchorPane|
|prefHeight|높이를 설정|AnchorPane|
|layoutX|컨트롤 X 좌표|컨트롤|
|layoutY|컨트롤 Y 좌표|컨트롤|
|< children >|컨트롤을 포함|AnchorPane

<br>
## HBox/VBox
- 수평과 수직으로 컨트롤을 배치하는 컨테이너

|태그 및 속성|설명|적용|
|---|---|---|
|prefWidth|폭을 설정|HBox, VBox|
|prefHeight|높이를 설정|HBox, VBox|
|alignment|컨트롤의 정렬을 설정|HBox, VBox|
|spacing|컨트롤의 간격을 설정|HBox, VBox|
|fillWidth|컨트롤의 폭 확장 여부 설정|VBox|
|fillHeight|컨트롤의 높이 확장 여부 설정|HBox, VBox|
|< children >|컨트롤을 포함|HBox, VBox|
|＜HBox.hgrow＞<br>&nbsp;&nbsp;&nbsp;＜Priority fx:constant="ALWAYS" /＞<br>＜/ HBox.hgrow ＞|HBox의 남은 폭을 채움|컨트롤|
|＜VBox.vgrow＞<br>&nbsp;&nbsp;&nbsp;＜Priority fx:constant="ALWAYS" /＞<br>＜/ VBox.vgrow ＞|VBox의 남은 높이를 채움|컨트롤|

<br>
## BorderPane
- top, bottom, left, right, center 셀에 컨트롤을 배치하는 컨테이너.
- 각 셀에는 하나의 컨트롤 또는 컨테이너만 배치할 수 있다.

|태그 및 속성|설명|적용|
|---|---|---|
|prefWidth|폭을 설정|BorderPane|
|prefHeight|높이를 설정|BorderPane|
|＜top＞|top에 배치될 컨트롤을 포함|BorderPane|
|＜bottom＞|bottom에 배치될 컨트롤을 포함|BorderPane|
|＜right＞|right에 배치될 컨트롤을 포함|BorderPane|
|＜left＞|left에 배치될 컨트롤을 포함|BorderPane|
|＜center＞|center에 배치될 컨트롤을 포함|BorderPane|

<br>
## FlowPane
- 행으로 컨트롤을 배치하는 컨테이너.
- 공간이 부족하면 새로운 행에 컨트롤을 배치한다.

|태그 및 속성|설명|적용|
|---|---|---|
|prefWidth|폭을 설정|FlowPane|
|prefHeight|높이를 설정|FlowPane|
|hgap|컨트롤의 수평 간격을 설정|FlowPane|
|vgap|컨트롤의 수직 간격을 설정|FlowPane|
|＜children＞|컨트롤을 포함|FlowPane|

<br>
## TilePane
- 고정된 크기의 셀(타일)에 행으로 컨트롤을 배치하는 컨테이너.
- 공간이 부족하면 새로운 행에 컨트롤을 배치한다.

|태그 및 속성|설명|적용|
|---|---|---|
|prefWidth|폭을 설정|TilePane|
|prefHeight|높이를 설정|TilePane|
|prefTileWidth|타일의 폭을 설정|TilePane|
|prefTitleHeight|타일의 높이를 설정|TilePane|
|＜children＞|컨트롤을 포함|TilePane|

<br>
## GridPane
- 격자 방식으로 컨트롤을 배치하는 컨테이너.
- 셀의 크기가 고정적이지 않고 유동적인 것이 특징.

|태그 및 속성|설명|적용|
|prefWidth|폭을 설정|GridPane|
|prefHeight|높이를 설정|GridPane|
|hgap|수평 컨트롤 간격을 설정|GridPane|
|vgap|수직 컨트롤 간격을 설정|GridPane|
|＜children＞|컨트롤을 포함|GridPane|
|GridPane.rowIndex|컨트롤이 위치하는 행 인덱스를 설정|컨트롤|
|GridPane.columnIndex|컨트롤이 위치하는 컬럼 인덱스를 설정|컨트롤|
|GridPane.rowSpan|행 병합 수를 설정|컨트롤|
|GridPane.columnSpan|컬럼 병합 수를 설정|컨트롤|
|GridPane.hgrow|수평 빈 공간 채우기를 설정|컨트롤|
|GridPane.vgrow|수직 빈 공간 채우기를 설정|컨트롤|
|GridPane.halignment|컨트롤의 수평 정렬을 설정|컨트롤|
|GridPane.valignment|컨트롤의 수직 정렬을 설정|컨트롤|

<br>
## StackPane
- 컨트롤을 겹쳐서 배치하는 컨테이너.
<br><br><br>
