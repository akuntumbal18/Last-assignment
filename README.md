# Last-assignment
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Davin Marciano E — Web Profile Preview</title>
  <meta name="description" content="Personal profile preview for Davin Marciano E." />
  <style>
    :root{
      /* All font colors set to #161d39 per request */
      --font-color: #161d39;
      --bg:#f6f7fb;
      --card: rgba(255,255,255,0.04);
      --accent1:#6C5CE7;
      --accent2:#00BFA6;
      --glass: rgba(255,255,255,0.03);
      --content-z: 1;
    }

    *{box-sizing:border-box}
    html,body{height:100%}
    html { scroll-behavior: smooth; } /* smooth scroll for anchor links */

    /* Page background: gradient with slight blur via pseudo-element */
    body{
      margin:0;
      font-family:Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      color:var(--font-color); /* global font color */
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.45;
      background-color: var(--bg); /* fallback */
      position:relative;
      z-index:var(--content-z);
      min-height:100vh;
    }
    /* Use ::before to render a soft, blurred gradient behind the content */
    body::before{
      content: "";
      position: fixed;
      inset: 0;
      z-index: -1;
      pointer-events: none;
      /* base gradient + accents */
      background-image:
        radial-gradient(600px 300px at 85% 10%, rgba(255,173,110,0.14), transparent 30%),
        radial-gradient(700px 420px at 20% 85%, rgba(86,156,255,0.12), transparent 30%),
        linear-gradient(120deg, rgba(255,243,236,1) 0%, rgba(245,250,255,1) 30%, rgba(242,235,255,1) 60%, rgba(255,250,242,1) 100%);
