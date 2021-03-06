project( GRAPHVIEWCTL )

set ( SRCS
		AESCrypto.cpp
		AESCrypto.h
		AggBitmap.cpp
		AggBitmap.h
		AggCommon.cpp
		AggCommon.h
		#AggDC.cpp
		AggDC.h
		AggGDIDC.cpp
		AggHDCRasterizer.cpp
		AggHDCRasterizer.h
		AggHitTest.cpp
		AggHitTest.h
		AggMemoryDC.cpp
		AggMemText.cpp
		AggMemText.h
		#AggRenderer.cpp
		#AggRenderer.h
		ArrowRendererImpl.cpp
		atlGraphView.h
		AttEdgeRenderer.cpp
		AttGraphRenderer.cpp
		AttSubgraphRenderer.cpp
		AttVertexRenderer.cpp
		AttVisGI.cpp
		AttVisGI.h
		Canvas.cpp
		Canvas.h
		circular.h
		config.cpp
		config.h
		DatasetRenderer.cpp
		DDrawSupport.cpp
		DDrawSupport.h
		DrawVertexHelper.cpp
		DrawVertexHelper.h
		DSeisintGraphControlEvents_CP.h
		Edge.cpp
		Edge.h
		EdgeRenderer.cpp
		FilterSubgraphEdges.cpp
		FilterSubgraphEdges.h
		FindDialog.cpp
		FruchtermanReingold.cpp
		FruchtermanReingold.h
		#gdi.cpp
		#gdi.h
		gdiimpl.h
		Geometry.cpp
		Geometry.h
		GraphContainer.cpp
		GraphContainer.h
		GraphRendererImpl.cpp
		GraphRendererImpl.h
		GraphTypes.cpp
		GraphTypes.h
		GraphViewCanvas.cpp
		GraphViewCanvas.h
		GraphViewContainer.cpp
		GraphViewContainer.h
		GraphViewControl.cpp
		GraphViewControl.h
		GraphViewCtl.rc
		GraphViewCtl.cpp
		GraphViewCtl.h
		GraphViewCtlApi.h
		#GraphViewCtlCommon.cpp
		#GraphViewCtlCommon.h
		#GraphViewDropTarget.h
		Hourglass.cpp
		Hourglass.h
		#IconRendererImpl.cpp
		ImageRendererImpl.cpp
		InputRenderer.cpp
		IOSubgraphRenderer.cpp
		ItemEditor.cpp
		ItemEditor.h
		layout.h
		layoutImpl.cpp
		layoutImpl.h
		Lee.cpp
		Lee.h
		LegacyEdgeRenderer.cpp
		LegacyGraphRenderer.cpp
		LegacyRenderImpl.h
		LegacySubgraphRenderer.cpp
		#LegacySubgraphRendererImpl.cpp
		LegacyVertexRenderer.cpp
		ListItemRendererImpl.cpp
		ListWindowRendererImpl.cpp
		MetaContainer.cpp
		MetaContainer.h
		neato.cpp
		neato.h
		NodePopup.cpp
		Notifications.h
		null.h
		OutputRenderer.cpp
		OverviewRenderer.cpp
		OverviewWnd.cpp
		OverviewWnd.h
		QueryBuilderUI.h
		ReferenceService.h
		render.h
		Renderer.h
		#renderImpl.cpp
		#renderImpl.h
		ScaledList.cpp
		ScaledList.h
		ScaledScrollBar.cpp
		ScaledScrollBar.h
		ScaledWindows.cpp
		ScaledWindows.h
		ScrollSupport.cpp
		ScrollSupport.h
		SizeTracker.h
		Subgraph.cpp
		Subgraph.h
		SVGParser.cpp
		SVGParser.h
		TextBoxRenderer.cpp
		ThreadTest.h
		TimelineCtrl.cpp
		TimelineCtrl.h
		TimelineDateTimeCtrl.h
		TimelineEdgeRederer.cpp
		TimelineGraphRenderer.cpp
		timelineLayout.cpp
		timelineLayout.h
		#TimelineVertexRenderer.cpp
		TouchGraph.cpp
		touchgraph.h
		Transform.cpp
		Transform.h
		Vertex.cpp
		Vertex.h
		VertexID.cpp
		VertexID.h
		#VertexRenderer.cpp
		#VertexRenderer.h
		#WebService.h
		#XGMMLParser.cpp
		#XGMMLParser.h
		XmlAnbSerializer.cpp
		XmlAnbSerializer.h
		
		../wtlex/DragDropImpl.cpp
		../wtlex/membm.cpp
		../wtlex/membm.h

		../cpptooltip/CeXDib.cpp
		../cpptooltip/CeXDib.h
		../cpptooltip/PPDrawManager.cpp
		../cpptooltip/PPDrawManager.h
		../cpptooltip/PPHtmlDrawer.cpp
		../cpptooltip/PPHtmlDrawer.h
		../cpptooltip/PPTooltip.cpp
		../cpptooltip/PPTooltip.h
	)

include_directories (
	../clib
	../comms

	../wtlex
	../wtltimeline
	
	${GRAPHLAYOUT_INCLUDE_DIRS}	
		
	${WTL_INCLUDE_DIR}/include

	${AGG_INCLUDE_DIRS}/include
	${AGG_INCLUDE_DIRS}/font_freetype
	${AGG_INCLUDE_DIRS}/agg2d

	${FREETYPE_INCLUDE_DIR_freetype2}/include
	${FREETYPE_INCLUDE_DIR_freetype2}/include/freetype
	
	${GRAPHVIZ_INCLUDE_DIRS}/lib/pathplan
	)

if (Boost_FOUND)
	include_directories ( ${Boost_INCLUDE_DIRS} )
	link_directories ( ${Boost_LIBRARY_DIRS} )
endif (Boost_FOUND)

ADD_MSVC_PRECOMPILED_HEADER("stdafx.h" "stdafx.cpp" SRCS)
add_library ( GRAPHVIEWCTL SHARED 
		${SRCS}
		
		GraphViewCtl_i.c

		aes/aes.h
		aes/aescpp.h
		aes/aescrypt.asm
		aes/aescrypt.c
		aes/aescrypt.mmx.asm
		aes/aeskey.c
		aes/aesopt.h
		aes/aestab.c
		aes/aestab.h
		aes/aesxam.c
		
		${AGG_INCLUDE_DIRS}/src/agg_arc.cpp
		${AGG_INCLUDE_DIRS}/src/agg_arrowhead.cpp
		${AGG_INCLUDE_DIRS}/src/agg_bezier_arc.cpp
		${AGG_INCLUDE_DIRS}/src/agg_bspline.cpp
		#${AGG_INCLUDE_DIRS}/src/agg_color_rgba.cpp
		${AGG_INCLUDE_DIRS}/src/agg_curves.cpp
		${AGG_INCLUDE_DIRS}/src/agg_embedded_raster_fonts.cpp
		${AGG_INCLUDE_DIRS}/src/agg_embedded_raster_fonts.cpp
		${AGG_INCLUDE_DIRS}/src/agg_gsv_text.cpp
		${AGG_INCLUDE_DIRS}/src/agg_image_filters.cpp
		${AGG_INCLUDE_DIRS}/src/agg_line_aa_basics.cpp
		${AGG_INCLUDE_DIRS}/src/agg_line_profile_aa.cpp
		${AGG_INCLUDE_DIRS}/src/agg_rounded_rect.cpp
		${AGG_INCLUDE_DIRS}/src/agg_sqrt_tables.cpp
		${AGG_INCLUDE_DIRS}/src/agg_trans_affine.cpp
		${AGG_INCLUDE_DIRS}/src/agg_trans_double_path.cpp
		${AGG_INCLUDE_DIRS}/src/agg_trans_single_path.cpp
		${AGG_INCLUDE_DIRS}/src/agg_trans_warp_magnifier.cpp
		${AGG_INCLUDE_DIRS}/src/agg_vcgen_bspline.cpp
		${AGG_INCLUDE_DIRS}/src/agg_vcgen_contour.cpp
		${AGG_INCLUDE_DIRS}/src/agg_vcgen_dash.cpp
		${AGG_INCLUDE_DIRS}/src/agg_vcgen_markers_term.cpp
		${AGG_INCLUDE_DIRS}/src/agg_vcgen_smooth_poly1.cpp
		${AGG_INCLUDE_DIRS}/src/agg_vcgen_stroke.cpp
		${AGG_INCLUDE_DIRS}/src/agg_vpgen_clip_polygon.cpp
		#${AGG_INCLUDE_DIRS}/src/agg_vpgen_clip_polyline.cpp
		${AGG_INCLUDE_DIRS}/src/agg_vpgen_segmentator.cpp

		${AGG_INCLUDE_DIRS}/font_win32_tt/agg_font_win32_tt.cpp
		#${AGG_INCLUDE_DIRS}/font_freetype/agg_font_freetype2.cpp

		#${AGG_INCLUDE_DIRS}/agg2d/agg2d.cpp
			
	)

add_dependencies ( GRAPHVIEWCTL
		CLIB
		COMMS
	)

SET ( FULL_LIBRARY_OUTPUT_PATH "${LIBRARY_OUTPUT_PATH}/${CMAKE_CFG_INTDIR}")

target_link_libraries( GRAPHVIEWCTL
		CLIB
		COMMS
		
		${GRAPHLAYOUT_LIBRARIES}
	)

install ( TARGETS 
			GRAPHVIEWCTL 
			RUNTIME DESTINATION bin )

install ( PROGRAMS 
			${GRAPHLAYOUT_DLL}
			DESTINATION bin )