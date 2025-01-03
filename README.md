# Ttw-JS--DrawSVGAPI

---

# 문의 사항

- thdtjsdn@gmail.com

---

# SVG Draw API 입니다.

- 많은 다량의 랜더링을 고려하여 성능 위주의 코드로 작성 되었습니다.

---

# 본 API는 '무료제공' 입니다.

- 자유롭게 사용하셔도 무방합니다.

---

# Sample source

- Example link
	- http://thdtjsdn.com:49310/app_tool/html_page/DrawSVG/index.html

```javascript
const CANVAS = TAPI.ge('ID-CANVAS');
const WEBGL = CANVAS.getContext('webgl');

const EVENT_LISTENERS = {

	Clear: function () {
		APIS.clearRect(SVG);
	}
	, Arc: function () {
		APIS.drawArc(SVG
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, getX_Random(), getY_Random(), getRadius_Random()
			, getArc_Random() * Math.PI / 2, Math.PI, false
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Circle: function () {
		APIS.drawCircle(SVG
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, getX_Random(), getY_Random(), getRadius_Random()
		);
		APIS.drawCircle_Fill(SVG, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getX_Random(), getY_Random(), getRadius_Random());
		APIS.drawCircle_Line(SVG, 5, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getX_Random(), getY_Random(), getRadius_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Rect: function () {
		APIS.drawRect(SVG
			, getX_Random(), getY_Random()
			, getX_Random() / 8, getY_Random() / 8
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);
		APIS.drawRect_Fill(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		APIS.drawRect_Line(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Line: function () {
		APIS.drawLine(SVG
			, getX_Random(), getY_Random(), getX_Random(), getY_Random()
			, getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, LineGradient: function () {
		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawLine_Gradient(SVG
			, getX_Random(), getY_Random(), getX_Random(), getY_Random()
			, getLineWidth_Random(), colorStops
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Polygon: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygon(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolygonGradientLinear: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }

		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawPolygon_Gradient_Linear(SVG, a, colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolygonGradientLinearCenter: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }

		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawPolygon_Gradient_Linear_Center(SVG, a, colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Polygon_Dashed_NN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygon_Dashed(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Polygon_Dashed_NNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygon_Dashed(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Polygon_Dashed_NNNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygon_Dashed(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, PolygonBezierCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygonBezierCurve(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolygonCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygonCurve(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	//----------------------------------------------------------------------------------------------------;

	, Polyline: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolyline(SVG, a, getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineGradientLinear: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }

		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawPolyline_Gradient_Linear(SVG, a, getLineWidth_Random(), colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineGradientLinearCenter: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }

		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawPolyline_Gradient_Linear_Center(SVG, a, getLineWidth_Random(), colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Polyline_Dashed_NN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolyline_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Polyline_Dashed_NNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolyline_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Polyline_Dashed_NNNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolyline_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, PolylineBezierCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineBezierCurve(SVG, a, getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineBezierCurve_Dashed_NN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineBezierCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolylineBezierCurve_Dashed_NNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineBezierCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolylineBezierCurve_Dashed_NNNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineBezierCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, PolylineCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineCurve(SVG, a, getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineCurve_Dashed_NN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolylineCurve_Dashed_NNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolylineCurve_Dashed_NNNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, PolylinePressureFront: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolyline__PressureFront(SVG, 2, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), a, 20);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, RegularPolygon: function () {
		APIS.drawRegularPolygon(SVG
			, getX_Random(), getY_Random(), getRadius_Random(), getSides_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, RegularPolygonGradientLinear: function () {
		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawRegularPolygon_Gradient_Linear(SVG, getX_Random(), getY_Random(), getRadius_Random(), getSides_Random(), colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, RegularPolygonRotation: function () {
		APIS.drawRegularPolygon_Rotation(SVG
			, getX_Random(), getY_Random(), getRadius_Random(), getSides_Random(), getRotation_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, GradientCircular: function () {
		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];
		APIS.drawGradient_Circular(SVG, getX_Random(), getY_Random(), getRadius_Random(), getRadius_Random(), colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, GradientLinear: function () {
		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];
		APIS.drawGradient_Linear(SVG, getX_Random(), getY_Random(), getX_Random(), getY_Random(), colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Bitmap: function () {
		var bitmap;
		function drawImage(bitmap) {
			APIS.drawImageBitmap(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, bitmap); // 이미지 객체, x 좌표, y 좌표, 너비, 높이
			if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(function () { drawImage(bitmap); }); }
		}
		const url = 'http://thdtjsdn.com:49310/app_thdtjsdn/html_page/Resume/index.photo.png';
		TAPI.w.apis.xhr.getResponseBlob(url, function (e) {
			bitmap = URL.createObjectURL(e.target.response);
			drawImage(bitmap);
		});
	}
	, BitmapRotation: function () {
		var bitmap;
		function drawImage(bitmap) {
			APIS.drawImageBitmap_Rotation(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, getRotationStyle_Random(), bitmap); // 비트맵 객체, x 좌표, y 좌표, 너비, 높이, 45도 회전
			if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(function () { drawImage(bitmap); }); }
		}
		const url = 'http://thdtjsdn.com:49310/app_thdtjsdn/html_page/Resume/index.photo.png';
		TAPI.w.apis.xhr.getResponseBlob(url, function (e) {
			bitmap = URL.createObjectURL(e.target.response);
			drawImage(bitmap);
		});
	}

	, Image: function () {
		const URL = 'http://thdtjsdn.com:49310/app_thdtjsdn/html_page/Resume/index.photo.png';
		APIS.drawImage(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, URL); // 이미지 객체, x 좌표, y 좌표, 너비, 높이
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, ImageRotation: function () {
		const URL = 'http://thdtjsdn.com:49310/app_thdtjsdn/html_page/Resume/index.photo.png';
		APIS.drawImage_Rotation(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, getRotationStyle_Random(), URL); // 이미지 객체, x 좌표, y 좌표, 너비, 높이
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Text: function () {
		APIS.drawText(SVG
			, getX_Random(), getY_Random()
			, 'THDTJSDN', getFontSize_Random() + 'px', 'Arial'
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, TextRotation: function () {
		APIS.drawText_Rotation(SVG
			, getX_Random(), getY_Random()
			, 'THDTJSDN', getFontSize_Random() + 'px', 'Arial'
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, getRotationStyle_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, TextLine: function () {
		APIS.drawText_Line(SVG
			, getX_Random(), getY_Random()
			, 'THDTJSDN', getFontSize_Random() + 'px', 'Arial'
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, TextLineRotation: function () {
		APIS.drawText_Line_Rotation(SVG
			, getX_Random(), getY_Random()
			, 'THDTJSDN', getFontSize_Random() + 'px', 'Arial'
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, getRotationStyle_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
};
```

---

# API 목록(필요할 법한 목록만)

- drawArc(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawCircle(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawRect(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawRect_Rotation(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawTriangle(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawTriangle_Rotation(WEBGL, FRAME_BUFFER_OBJECT, ...)

- drawImageBitmap(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawImageBitmap_Rotation(WEBGL, FRAME_BUFFER_OBJECT, ...)

- drawLine(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawLineDashed(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawLineThick(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawLineThickDashed(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawLineThickGradient(WEBGL, FRAME_BUFFER_OBJECT, ...)

- drawPolygon(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolygonBezierCurve(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolygonCurve(WEBGL, FRAME_BUFFER_OBJECT, ...)

- drawPolyline(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolylineBezierCurve(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolylineBezierCurveThick(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolylineCurve(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawPolylineCurveThick(WEBGL, FRAME_BUFFER_OBJECT, ...)

- drawRegularPolygon(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawRegularPolygon_Rotation(WEBGL, FRAME_BUFFER_OBJECT, ...);

- drawText(WEBGL, FRAME_BUFFER_OBJECT, ...)
- drawText_Rotation(WEBGL, FRAME_BUFFER_OBJECT, ...)

---