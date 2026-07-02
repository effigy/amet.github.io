<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Adaptive Music Toolbox</title>
  <meta name="description" content="Grade 3 music activities with adaptive classroom supports.">
  <style>
    body {
      margin: 0;
      background: #edf5fa;
      color: #233142;
      font-family: "Calibri", Verdana, Arial, sans-serif;
    }

    main, footer {
      max-width: 1040px;
      margin: auto;
      padding: 0 16px;
    }

    section { padding: 22px 0; }
    .top { max-width: 760px; padding-top: 30px; }

    h1 { font-size: 48px; line-height: 1; margin-bottom: 10px; }
    h2 { margin-bottom: 8px; }
    h3 { margin-bottom: 10px; }

    .small-title { color: #1f587c; font-size: 13px; font-weight: bold; }
    .note, .muted, footer { color: #667789; }
    a { color: #1f587c; font-weight: bold; }
    button { font: inherit; }

    .activity-grid, .choice-grid, .details, .media-grid {
      display: grid;
      gap: 12px;
    }

    .activity-grid { grid-template-columns: repeat(3, 1fr); }
    .choice-grid, .details, .media-grid { grid-template-columns: repeat(2, 1fr); }

    .activity-card, .box, .choice, .lesson-head, .detail, .media-card {
      border: 1px solid #bcd2e2;
      border-radius: 14px;
      background: #fff;
      box-shadow: 2px 2px 0 rgba(45,116,163,.12);
    }

    .activity-card {
      padding: 0;
      color: #233142;
      text-align: left;
      overflow: hidden;
      cursor: pointer;
    }

    .activity-card:hover, .activity-card.selected, .choice:hover, .choice.selected {
      border-color: #2d74a3;
      background: #dcecf6;
    }

    .activity-card img {
      width: 100%;
      height: 150px;
      object-fit: cover;
    }

    .card-text { display: block; padding: 12px; }
    .card-text b, .card-text span, .choice b, .choice span, .detail span, .detail b { display: block; }
    .card-text span, .choice span, .detail span { color: #667789; font-size: 14px; }

    .box { padding: 16px; margin-bottom: 14px; }
    .option-set { margin-top: 18px; }

    .line-head {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 10px;
    }

    .clear-btn {
      border: 0;
      background: transparent;
      color: #1f587c;
      text-decoration: underline;
      cursor: pointer;
    }

    .choice {
      min-height: 60px;
      padding: 12px;
      color: #233142;
      text-align: left;
      cursor: pointer;
    }

    .lesson-head {
      display: grid;
      grid-template-columns: 280px 1fr;
      overflow: hidden;
      margin-bottom: 14px;
    }

    .lesson-head img {
      width: 100%;
      height: 100%;
      min-height: 220px;
      object-fit: cover;
    }

    .lesson-head div { padding: 16px; }
    .detail { padding: 10px; background: #f9fcfe; }

    .ways {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      padding: 0;
      list-style: none;
    }

    .ways li {
      padding: 8px 10px;
      border: 1px solid #bcd2e2;
      border-radius: 20px;
      background: #f9fcfe;
    }

    .step {
      display: grid;
      grid-template-columns: 44px 1fr;
      gap: 10px;
      border-top: 1px solid #bcd2e2;
      padding: 12px 0;
    }

    .step:first-child { border-top: 0; }

    .number {
      width: 32px;
      height: 32px;
      border: 1px solid #bcd2e2;
      border-radius: 50%;
      background: #dcecf6;
      color: #1f587c;
      font-weight: bold;
      line-height: 32px;
      text-align: center;
    }

    .add {
      padding: 10px;
      border-left: 4px solid #2d74a3;
      background: #f9fcfe;
    }

    .media-card {
      display: grid;
      grid-template-columns: 110px 1fr;
      gap: 12px;
      padding: 12px;
      background: #f9fcfe;
    }

    .media-card img {
      width: 110px;
      height: 80px;
      object-fit: cover;
    }

    footer { padding-bottom: 28px; font-size: 14px; }

    @media (max-width: 850px) {
      h1 { font-size: 38px; }
      .activity-grid, .choice-grid, .lesson-head, .media-grid { grid-template-columns: 1fr; }
    }

    @media (max-width: 540px) {
      .details, .step, .media-card { grid-template-columns: 1fr; }
      .media-card img { width: 100%; height: 140px; }
    }
  </style>
</head>
<body>
  <main>
    <section class="top">
      <p class="small-title">Music class, remixed</p>
      <h1>Pick a lesson. Tune it for your room.</h1>
      <p class="intro muted">Choose an activity, tap the tools you have, and pick the supports your students may need. The plan changes as you click.</p>
    </section>

    <section>
      <p class="small-title">Step 1</p>
      <h2>Choose today’s activity</h2>
      <p class="note">The plan below will adapt the activity you select.</p>
      <div class="activity-grid">
        <button class="activity-card" type="button" data-activity="score-on-the-floor">
          <img src="https://carnegiehall.imgix.net:443/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Score-on-the-Floor.jpg?w=1200&amp;h=630&amp;fit=crop&amp;crop=faces" alt="Score on the Floor">
          <span class="card-text">
            <b>Score on the Floor</b>
            <span>Students explore absolute pitch through movement and games.</span>
          </span>
        </button>
        <button class="activity-card" type="button" data-activity="musical-mapping">
          <img src="https://carnegiehall.imgix.net:443/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Musical-Mapping.jpg?w=1200&amp;h=630&amp;fit=crop&amp;crop=faces" alt="Musical Mapping—First and Second Endings">
          <span class="card-text">
            <b>Musical Mapping—First and Second Endings</b>
            <span>Students explore first and second endings by singing and moving.</span>
          </span>
        </button>
        <button class="activity-card" type="button" data-activity="composing-meters">
          <img src="https://carnegiehall.imgix.net:443/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Composing-in-Simple-and-Compound-Meters.jpg?w=1200&amp;h=630&amp;fit=crop&amp;crop=faces" alt="Composing in Simple and Compound Meters">
          <span class="card-text">
            <b>Composing in Simple and Compound Meters</b>
            <span>Students compose and notate short rhythms in 4/4, 3/4, and 6/8 meters across multiple class periods.</span>
          </span>
        </button>
      </div>
    </section>

    <section id="customize">
      <p class="small-title">Step 2</p>
      <h2>Describe Your Class:</h2>
      <div class="box">
        <div class="option-set">
          <div class="line-head">
            <h3>Tools in the room</h3>
            <button class="clear-btn" id="clearTools" type="button">Clear</button>
          </div>
          <div class="choice-grid">
          <button class="choice" type="button" data-kind="tool" data-id="projector">
            <b>Big screen / projector</b>
            <span>Show the staff, route, or rhythm pattern where everyone can see it.</span>
          </button>
          <button class="choice" type="button" data-kind="tool" data-id="tablet">
            <b>Tablet or touchscreen</b>
            <span>Let students move notes, routes, or rhythms with a tap or drag.</span>
          </button>
          <button class="choice" type="button" data-kind="tool" data-id="headphones">
            <b>Headphones / volume choice</b>
            <span>Give students a quieter way to listen or practice.</span>
          </button>
          <button class="choice" type="button" data-kind="tool" data-id="quiet-percussion">
            <b>Quiet percussion</b>
            <span>Use soft taps, pads, scarves, or body signs instead of loud sounds.</span>
          </button>
          <button class="choice" type="button" data-kind="tool" data-id="adaptive-switches">
            <b>Switches / alternate controllers</b>
            <span>Trigger notes, beats, choices, or directions with accessible controls.</span>
          </button>
          <button class="choice" type="button" data-kind="tool" data-id="visual-cards">
            <b>Visual cards</b>
            <span>Use cards for notes, signs, meters, roles, and step-by-step reminders.</span>
          </button>
          <button class="choice" type="button" data-kind="tool" data-id="floor-space">
            <b>Floor space</b>
            <span>Use a floor staff, classroom route, or movement area.</span>
          </button>
          <button class="choice" type="button" data-kind="tool" data-id="small-groups">
            <b>Small groups</b>
            <span>Let students try things safely before sharing with the whole class.</span>
          </button>
          <button class="choice" type="button" data-kind="tool" data-id="preferred-music">
            <b>Student-picked music</b>
            <span>Use familiar songs, hooks, or class-created music when it fits.</span>
          </button>
          <button class="choice" type="button" data-kind="tool" data-id="metronome">
            <b>Metronome / pulse track</b>
            <span>Keep the beat steady without making the room louder.</span>
          </button>
          <button class="choice" type="button" data-kind="tool" data-id="no-tech">
            <b>Low-tech only</b>
            <span>Use paper, bodies, cards, roles, and classroom materials.</span>
          </button>
          </div>
        </div>
        <div class="option-set">
          <div class="line-head">
            <h3>Things to make easier</h3>
            <button class="clear-btn" id="clearNeeds" type="button">Clear</button>
          </div>
          <div class="choice-grid">
          <button class="choice" type="button" data-kind="need" data-id="sound-sensitivity">
            <b>Sounds feel like a lot</b>
            <span>Lower volume and make sound more predictable.</span>
          </button>
          <button class="choice" type="button" data-kind="need" data-id="motor-access">
            <b>Movement access</b>
            <span>Offer ways to join without fast walking, jumping, or standing.</span>
          </button>
          <button class="choice" type="button" data-kind="need" data-id="social-exposure">
            <b>Performance pressure</b>
            <span>Make sharing feel safe and optional.</span>
          </button>
          <button class="choice" type="button" data-kind="need" data-id="notation-difficulty">
            <b>Notation is tricky</b>
            <span>Connect symbols to movement, pictures, words, or icons.</span>
          </button>
          <button class="choice" type="button" data-kind="need" data-id="working-memory">
            <b>Too many steps at once</b>
            <span>Keep directions visible and break tasks into chunks.</span>
          </button>
          <button class="choice" type="button" data-kind="need" data-id="attention-focus">
            <b>Focus support</b>
            <span>Make the goal, role, and current step easy to spot.</span>
          </button>
          <button class="choice" type="button" data-kind="need" data-id="choice-overload">
            <b>Too many choices</b>
            <span>Offer a few good choices instead of a wide-open menu.</span>
          </button>
          <button class="choice" type="button" data-kind="need" data-id="group-pacing">
            <b>Different pacing</b>
            <span>Build in practice time and flexible roles.</span>
          </button>
          <button class="choice" type="button" data-kind="need" data-id="nonverbal-options">
            <b>Non-speaking options</b>
            <span>Let students point, gesture, choose cards, or direct a partner.</span>
          </button>
          <button class="choice" type="button" data-kind="need" data-id="challenge-extension">
            <b>Ready for more</b>
            <span>Add challenge without making other paths feel lesser.</span>
          </button>
          </div>
        </div>
      </div>
    </section>

    <section>
      <p class="small-title">Step 3</p>
      <h2>Your plan</h2>
      <p class="note">Materials and steps update to match your choices.</p>
      <div id="plan"></div>
    </section>

    <section>
      <p class="small-title">Links</p>
      <h2>Videos and handouts</h2>
      <p class="note">Helpful Carnegie Hall materials for the selected activity.</p>
      <div id="links"></div>
    </section>
  </main>

  <footer>
    <p>Original activity text and media links are from Carnegie Hall Music Educators Toolbox Grade 3. Except where otherwise noted, this page is shared under the Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License.</p>
  </footer>

  <script>
    var activities = [
    {
        "id": "score-on-the-floor",
        "title": "Score on the Floor",
        "sourceUrl": "https://www.carnegiehall.org/Education/Programs/Music-Educators-Toolbox/3-Score-on-the-Floor",
        "heroImage": "https://carnegiehall.imgix.net:443/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Score-on-the-Floor.jpg?w=1200&h=630&fit=crop&crop=faces",
        "metadata": {
            "aim": "What are the notes on the treble staff?",
            "summary": "Students explore absolute pitch through movement and games.",
            "grade": "3rd",
            "concept": "Pitch"
        },
        "baseMaterials": [
            "Five horizontal lines of tape for a floor staff",
            "Letter-name labels for each line and space",
            "Paper covers for labels",
            "Pitched instrument",
            "Optional movable paper ledger lines"
        ],
        "original": {
            "instructions": [
                "Create a staff on the floor using five horizontal lines of tape. Label each line and space with the appropriate letter name but cover the letter with a piece of paper.",
                "Review lines and spaces by having students walk in steps and jump in leaps on the floor staff.",
                "Play an A on a pitched instrument and ask students to stand on the space for A. Check students\u2019 response by revealing the name for the A space.",
                "Play a B and direct students to move up a step (ensure that they move to the B line, not the C space). What comes after A in the alphabet? Let\u2019s see if we are right! (Reveal label on the B line.)",
                "Continue to play the next ascending notes in steps and reveal the notes up to G above the staff. In music, this is where our alphabet ends. How many letters do we have? On what letters did we start and end?",
                "Return students to A on the staff. Play a G and direct students to move down a step and introduce/reveal the musical alphabet descending to E on the staff.",
                "Review each letter name ascending and descending by playing each pitch by step or leap, and have students move up or down and speak the note name."
            ],
            "goingDeeper": [
                "Ask for a small group of volunteers to spell out words on the staff (one student per letter). The rest of the class will give a thumbs-up if the word is spelled correctly or raise their hand to help a friend make a correction.",
                "Write the letter names of a well-known classroom song on the board and ask students to stand on the staff to represent the notes of the song. Sing through the song on letter names until students recognize the song, then sing through with lyrics.",
                "Introduce ledger lines with movable pieces of paper and remove staff labels as students become comfortable with the staff."
            ]
        },
        "resources": {
            "worksheets": [],
            "assessments": [
                {
                    "title": "3rd Grade Formative Assessment: Pitch (PDF)",
                    "url": "https://www.carnegiehall.org/-/media/CarnegieHall/Files/PDFs/Education/Educators/Toolbox/Grade-3/Toolbox-Grade-3-Formative-Assessment-Pitch.pdf?la=en",
                    "image": "https://carnegiehall.imgix.net/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Formative-Assessment-Pitch-N-UP.jpg?w=301&h=406&fit=crop&crop=faces",
                    "alt": "Pitch student worksheet"
                },
                {
                    "title": "3rd Grade Summative Assessment (PDF)",
                    "url": "https://www.carnegiehall.org/-/media/CarnegieHall/Files/PDFs/Education/Educators/Toolbox/Grade-3/Toolbox-Grade-3-Summative-Assessment.pdf?la=en",
                    "image": "https://carnegiehall.imgix.net/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Summative-Assessment-N-UP.jpg?w=301&h=406&fit=crop&crop=faces",
                    "alt": "Summative Assessment Teacher Worksheet table of contents with scope of musical concepts"
                }
            ]
        },
        "videos": [
            {
                "title": "Grade 3 Activity Demo: Pitch",
                "vimeoId": "111863549",
                "image": "https://carnegiehall.imgix.net/-/media/Feature/BrightCove/Import-Images/Staff-Hopscotch-Pitch-Activity.jpeg?w=1920&h=1080",
                "summary": "Carnegie Hall demo: \u201cStaff Hopscotch.\u201d Students explore absolute pitch through movement and games."
            },
            {
                "title": "Grade 3 Summative Assessment Demo: Pitch/Rhythm and Meter",
                "vimeoId": "111863921",
                "image": "https://carnegiehall.imgix.net/-/media/Feature/BrightCove/Import-Images/Staff-Hopscotch-Pitch-Rhythm-and-Meter-Summative-Assessment.jpeg?w=1920&h=1080",
                "summary": "Carnegie Hall demo: \u201cCompose a Melody.\u201d Students identify pitches and compose a two-measure melody using the Student Worksheet."
            },
            {
                "title": "Grade 3 Summative Assessment Demo: Pitch/Form Design",
                "vimeoId": "111863926",
                "image": "https://carnegiehall.imgix.net/-/media/Feature/BrightCove/Import-Images/Staff-Hopscotch-Pitch-Form-and-Design-Summative-Assessment.jpeg?w=1920&h=1080",
                "summary": "Carnegie Hall demo: \u201cSight Read a Melody.\u201d Students sight sing or play four measures with first and second endings using the Student Worksheet."
            }
        ],
        "rules": [
            {
                "id": "score-base",
                "materials": [
                    "Role cards for mover, pointer, note caller, checker, and partner coach"
                ],
                "setup": [
                    "Before you begin, show the class the different ways students can join."
                ],
                "participation": [
                    "Move on the staff",
                    "Point from a seat",
                    "Call or choose note names",
                    "Check answers with thumbs-up or a help signal"
                ],
                "always": true
            },
            {
                "id": "score-projected-staff",
                "materials": [
                    "Projected staff or large paper staff",
                    "Moveable note marker",
                    "Optional student markers"
                ],
                "setup": [
                    "Place a projected or paper staff next to the floor staff. Use it as another version of the floor space."
                ],
                "participation": [
                    "Move an icon to the pitch",
                    "Tell a partner where to move",
                    "Use a pointer, switch, or card to choose the line or space"
                ],
                "stepNotes": {
                    "2": [
                        "When students hear A, they can stand on A, move a marker to A, or choose the A card."
                    ],
                    "3": [
                        "Ask the B question while students move bodies, icons, or cards up one step."
                    ],
                    "6": [
                        "Review by moving a marker through steps and leaps while a partner names the notes."
                    ]
                },
                "tools": [
                    "projector",
                    "tablet"
                ],
                "needs": [
                    "motor-access",
                    "notation-difficulty",
                    "nonverbal-options",
                    "social-exposure"
                ]
            },
            {
                "id": "score-small-group",
                "materials": [
                    "Mini staff cards or small tape staffs for stations"
                ],
                "setup": [
                    "Start in pairs or trios. Invite groups to share when they feel ready."
                ],
                "participation": [
                    "Practice at a station",
                    "Be the note checker",
                    "Choose a partner to represent the group"
                ],
                "stepNotes": {
                    "1": [
                        "Try steps and leaps in small groups before moving to the big staff."
                    ],
                    "5": [
                        "Let groups practice going down the staff before asking the full class."
                    ]
                },
                "tools": [
                    "small-groups",
                    "visual-cards",
                    "no-tech"
                ],
                "needs": [
                    "attention-focus",
                    "choice-overload",
                    "group-pacing",
                    "social-exposure",
                    "working-memory"
                ]
            },
            {
                "id": "score-interest",
                "materials": [
                    "Short note-name hooks or melodies from familiar songs or student-composed music"
                ],
                "setup": [
                    "Pick one short melody. Show only the note letters students need for this activity."
                ],
                "participation": [
                    "Place notes from a familiar hook on the staff",
                    "Find the steps and leaps in the hook or melody"
                ],
                "stepNotes": {
                    "6": [
                        "After the review, map a short melody with bodies, icons, or note cards."
                    ]
                },
                "tools": [
                    "preferred-music"
                ],
                "needs": [
                    "attention-focus",
                    "challenge-extension",
                    "notation-difficulty"
                ]
            },
            {
                "id": "score-gentle-sound",
                "materials": [
                    "Quieter pitched instrument or lower-volume setting",
                    "Simple volume cue card",
                    "Soft tap cue or steady pulse"
                ],
                "setup": [
                    "Keep pitch examples short and predictable. Use a soft tap or steady pulse if it helps the class know when to listen, choose, and reveal."
                ],
                "participation": [
                    "Listen with headphones if helpful",
                    "Point to up, down, step, or leap on a mat, whiteboard, or projector instead of answering aloud"
                ],
                "stepNotes": {
                    "2": [
                        "Play A at a comfortable volume, then give students a moment to choose the space."
                    ],
                    "6": [
                        "Use a steady pattern: play, wait, move or point, then reveal."
                    ]
                },
                "tools": [
                    "headphones",
                    "metronome",
                    "no-tech",
                    "quiet-percussion"
                ],
                "needs": [
                    "sound-sensitivity",
                    "attention-focus",
                    "working-memory"
                ]
            },
            {
                "id": "score-continuum",
                "materials": [
                    "Pitch slider picture or simple hand-sign scale",
                    "Icon cards for line, space, up, down, step, and leap"
                ],
                "setup": [
                    "Use visual or icon cards next to standard staff language at first. Fade them when the class is ready."
                ],
                "participation": [
                    "Glide a hand or pointer between notes",
                    "Guess where the pitch will land"
                ],
                "stepNotes": {
                    "4": [
                        "Pause after G and show that staff notes are points in a larger pitch space."
                    ],
                    "6": [
                        "Ask whether the pitch moved by step, by leap, or somewhere in between.",
                        "During review, students can use icon cards first, then match the icon to the letter name."
                    ],
                    "1": [
                        "Let students use visual or icon cards for line, space, step, and leap before they answer with standard notation words."
                    ]
                },
                "tools": [
                    "projector",
                    "visual-cards",
                    "no-tech"
                ],
                "needs": [
                    "notation-difficulty",
                    "challenge-extension"
                ]
            },
            {
                "id": "score-floor-options",
                "materials": [
                    "Clear floor path around the staff",
                    "Chair or seated pointer spot"
                ],
                "setup": [
                    "Keep the floor staff available, but make it one choice rather than the only way to join."
                ],
                "participation": [
                    "Step on the staff",
                    "Point from the edge",
                    "Direct a partner on the staff"
                ],
                "stepNotes": {
                    "1": [
                        "Students can walk the staff, point to the next spot, or direct a partner through steps and leaps."
                    ],
                    "5": [
                        "For the descending review, let students choose moving, pointing, or coaching."
                    ]
                },
                "tools": [
                    "floor-space",
                    "small-groups",
                    "no-tech"
                ],
                "needs": [
                    "motor-access",
                    "social-exposure",
                    "group-pacing",
                    "choice-overload"
                ]
            },
            {
                "id": "score-switch-answer",
                "materials": [
                    "Two-choice note cards",
                    "Line and space cards",
                    "Optional switch or button for choosing"
                ],
                "setup": [
                    "Use small answer sets. Two or three good choices are enough for a quick round."
                ],
                "participation": [
                    "Choose a note card",
                    "Use a switch or button to answer",
                    "Point to line or space"
                ],
                "stepNotes": {
                    "2": [
                        "For A, students can stand on the staff, choose the A card, point to the A space, or use a switch to answer."
                    ],
                    "3": [
                        "When moving to B, offer a line/space choice card so the notation jump is visible."
                    ],
                    "6": [
                        "In review, show two or three choices at a time. This keeps the game moving without making the notation feel like a test."
                    ]
                },
                "tools": [
                    "adaptive-switches",
                    "visual-cards",
                    "tablet"
                ],
                "needs": [
                    "motor-access",
                    "notation-difficulty",
                    "nonverbal-options",
                    "choice-overload",
                    "working-memory"
                ]
            }
        ]
    },
    {
        "id": "musical-mapping",
        "title": "Musical Mapping\u2014First and Second Endings",
        "sourceUrl": "https://www.carnegiehall.org/Education/Programs/Music-Educators-Toolbox/3-Musical-Mapping",
        "heroImage": "https://carnegiehall.imgix.net:443/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Musical-Mapping.jpg?w=1200&h=630&fit=crop&crop=faces",
        "metadata": {
            "aim": "How are first and second endings used in music?",
            "summary": "Students explore first and second endings by singing and moving.",
            "grade": "3rd",
            "concept": "Form"
        },
        "baseMaterials": [
            "Road signs with arrows and musical symbols",
            "Start, First Ending, Second Ending, and Stop signs",
            "Teacher Worksheet PDF",
            "Song with first and second endings",
            "Optional route cards or desk map"
        ],
        "original": {
            "instructions": [
                "Hang road signs with arrows and musical symbols around your room that read Start, First Ending, Second Ending, and Stop. Download Teacher Worksheet (PDF)",
                "Play, sing, or improvise any song with a first and second ending. Lead a few students around the room, singing and following the arrows while others watch. Repeat (rotating students) and stop at each sign to discuss the route.",
                "When students are comfortable with the route, first with direction and then on their own, point out and discuss the symbols on the signs. These are road signs for musicians. They tell us where to go in our music.",
                "What visual clues does each symbol tell you about what to do in the music?",
                "Try again with a different song with first and second endings and prompt students to figure out where to go on your classroom highway!"
            ],
            "goingDeeper": [
                "Compose a short class composition with first and second endings."
            ]
        },
        "resources": {
            "worksheets": [
                {
                    "title": "Download Teacher Worksheet (PDF)",
                    "url": "https://www.carnegiehall.org/-/media/CarnegieHall/Files/PDFs/Education/Educators/Toolbox/Grade-3/Toolbox-Grade-3-Musical-Mapping-First-and-Second-Endings.pdf?la=en&hash=5A575D48B5286FEFAF789E087C114300"
                }
            ],
            "assessments": [
                {
                    "title": "3rd Grade Formative Assessment: Form (PDF)",
                    "url": "https://www.carnegiehall.org/-/media/CarnegieHall/Files/PDFs/Education/Educators/Toolbox/Grade-3/Toolbox-Grade-3-Formative-Assessment-Form-and-Design.pdf?la=en",
                    "image": "https://carnegiehall.imgix.net/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Formative-Assessment-Form-and-Design-N-UP.jpg?w=301&h=406&fit=crop&crop=faces",
                    "alt": "Form and Design student worksheet"
                },
                {
                    "title": "3rd Grade Summative Assessment (PDF)",
                    "url": "https://www.carnegiehall.org/-/media/CarnegieHall/Files/PDFs/Education/Educators/Toolbox/Grade-3/Toolbox-Grade-3-Summative-Assessment.pdf?la=en",
                    "image": "https://carnegiehall.imgix.net/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Summative-Assessment-N-UP.jpg?w=301&h=406&fit=crop&crop=faces",
                    "alt": "Summative Assessment Teacher Worksheet table of contents with scope of musical concepts"
                }
            ]
        },
        "videos": [
            {
                "title": "Grade 3 Activity Demo: Form and Design",
                "vimeoId": "111863548",
                "image": "https://carnegiehall.imgix.net/-/media/Feature/BrightCove/Import-Images/Musical-Mapping-Form-and-Design-Activity.jpeg?w=1920&h=1080",
                "summary": "Carnegie Hall demo: \u201cMusical Mapping\u2014First and Second Endings.\u201d Students explore first and second endings by singing and moving."
            },
            {
                "title": "Grade 3 Summative Assessment Demo: Pitch/Form Design",
                "vimeoId": "111863926",
                "image": "https://carnegiehall.imgix.net/-/media/Feature/BrightCove/Import-Images/Musical-Mapping-Pitch-Form-and-Design-Summative-Assessment.jpeg?w=1920&h=1080",
                "summary": "Carnegie Hall demo: \u201cSight Read a Melody.\u201d Students sight sing or play four measures with first and second endings using the Student Worksheet."
            }
        ],
        "rules": [
            {
                "id": "map-base",
                "materials": [
                    "Role cards for navigator, singer, sign holder, map reader, observer, and composer"
                ],
                "setup": [
                    "Introduce the jobs as normal parts of the activity. No job is the \u201cspecial\u201d job."
                ],
                "participation": [
                    "Walk the route",
                    "Hold or point to signs",
                    "Track the route on a desk map",
                    "Sing, hum, tap, conduct, or signal the next turn"
                ],
                "always": true
            },
            {
                "id": "map-sensory",
                "materials": [
                    "Lower-volume recording or teacher voice",
                    "Quiet listening option",
                    "Clear start and stop signal",
                    "Soft pulse cue"
                ],
                "setup": [
                    "Set a calm volume. Use a soft pulse cue if it helps students know when the group is moving to the next sign."
                ],
                "participation": [
                    "Follow on a desk map first",
                    "Use headphones during examples when helpful",
                    "Be the start or stop signaler"
                ],
                "stepNotes": {
                    "1": [
                        "Walk the route quietly first. Add singing after the path makes sense."
                    ],
                    "4": [
                        "Choose the second song from options that feel comfortable in volume, tempo, and repetition."
                    ]
                },
                "tools": [
                    "headphones",
                    "metronome",
                    "no-tech",
                    "quiet-percussion"
                ],
                "needs": [
                    "sound-sensitivity",
                    "attention-focus",
                    "working-memory"
                ]
            },
            {
                "id": "map-social",
                "materials": [
                    "Station maps or floor arrows for two or three small routes"
                ],
                "setup": [
                    "Let teams practice with the same symbols at small stations first."
                ],
                "participation": [
                    "Be the team navigator",
                    "Read the map instead of moving",
                    "Practice with a partner first"
                ],
                "stepNotes": {
                    "1": [
                        "Lead one small team while the rest of the class tracks the route on paper or with hand signs."
                    ],
                    "2": [
                        "Talk about the symbols using a map, not only the students who moved."
                    ]
                },
                "tools": [
                    "small-groups",
                    "floor-space",
                    "no-tech"
                ],
                "needs": [
                    "social-exposure",
                    "group-pacing",
                    "motor-access"
                ]
            },
            {
                "id": "map-choices",
                "materials": [
                    "First-then route strip",
                    "Two-choice participation cards",
                    "Symbol key",
                    "Icon cards for Start, Repeat, First Ending, Second Ending, and Stop"
                ],
                "setup": [
                    "Use icon cards for the route first, then connect each icon to the standard music symbol."
                ],
                "participation": [
                    "Pick from a short role menu",
                    "Use a first-then card to follow the endings"
                ],
                "stepNotes": {
                    "2": [
                        "Show the path: Start \u2192 First Ending \u2192 Repeat \u2192 Second Ending \u2192 Stop.",
                        "Students can follow the icon route before reading the standard symbols."
                    ],
                    "3": [
                        "Match each symbol to one action before asking for open answers.",
                        "Let students point to an icon card if explaining the symbol out loud is not the best fit."
                    ]
                },
                "tools": [
                    "visual-cards",
                    "no-tech"
                ],
                "needs": [
                    "choice-overload",
                    "working-memory",
                    "notation-difficulty",
                    "nonverbal-options"
                ]
            },
            {
                "id": "map-screen-or-touch-map",
                "materials": [
                    "Projected route map or tablet map",
                    "Moveable marker for the class route"
                ],
                "setup": [
                    "Show the path on a screen or tablet so students can follow without crossing the room."
                ],
                "participation": [
                    "Move the route marker",
                    "Point to the next sign",
                    "Direct a partner on the floor route"
                ],
                "stepNotes": {
                    "1": [
                        "Students can follow the first route on the map while a small group walks it."
                    ],
                    "2": [
                        "Use the map to connect each symbol with the next action."
                    ],
                    "4": [
                        "Before moving, let students predict the route on the screen or tablet."
                    ]
                },
                "tools": [
                    "projector",
                    "tablet"
                ],
                "needs": [
                    "motor-access",
                    "notation-difficulty",
                    "nonverbal-options",
                    "attention-focus"
                ]
            },
            {
                "id": "map-interest-extension",
                "materials": [
                    "Teacher-picked songs with first and second endings or repeat-like form",
                    "Optional repeat sign card"
                ],
                "setup": [
                    "Start with a comfortable song. Bring in familiar or trickier examples after students know the route."
                ],
                "participation": [
                    "Vote from teacher-picked songs",
                    "Build a short class route",
                    "Add repeat signs after the base route works"
                ],
                "stepNotes": {
                    "4": [
                        "Use a familiar example and ask students to predict the route before moving."
                    ],
                    "5": [
                        "If students compose, let them build the form with cards before performing it."
                    ]
                },
                "tools": [
                    "preferred-music"
                ],
                "needs": [
                    "attention-focus",
                    "challenge-extension",
                    "sound-sensitivity"
                ]
            },
            {
                "id": "map-switch-route",
                "materials": [
                    "Next-sign cards",
                    "Optional switch or button for choosing the next stop",
                    "Small route board"
                ],
                "setup": [
                    "Give students a way to choose or direct the route without having to walk the whole classroom path."
                ],
                "participation": [
                    "Choose the next sign",
                    "Press a switch for repeat or stop",
                    "Direct a partner on the route"
                ],
                "stepNotes": {
                    "1": [
                        "A student can use cards, a switch, or a partner to choose the next sign while a small group walks the route."
                    ],
                    "4": [
                        "Before the class moves, ask students to choose the next sign with a card, point, or switch."
                    ]
                },
                "tools": [
                    "adaptive-switches",
                    "visual-cards",
                    "tablet"
                ],
                "needs": [
                    "motor-access",
                    "nonverbal-options",
                    "notation-difficulty",
                    "choice-overload"
                ]
            }
        ]
    },
    {
        "id": "composing-meters",
        "title": "Composing in Simple and Compound Meters",
        "sourceUrl": "https://www.carnegiehall.org/Education/Programs/Music-Educators-Toolbox/3-Composing-in-Simple-and-Compound-Meters",
        "heroImage": "https://carnegiehall.imgix.net:443/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Composing-in-Simple-and-Compound-Meters.jpg?w=1200&h=630&fit=crop&crop=faces",
        "metadata": {
            "aim": "How can we create and perform rhythmic patterns in simple and compound meters?",
            "summary": "Students compose and notate short rhythms in 4/4, 3/4, and 6/8 meters across multiple class periods.",
            "grade": "3rd",
            "concept": "Rhythm & Meter; Form"
        },
        "baseMaterials": [
            "Musical examples in 4/4, 3/4, and 6/8",
            "Teacher Worksheet PDF",
            "Student Worksheet PDF",
            "Board or display for class rhythm patterns",
            "Writing tools or rhythm cards"
        ],
        "original": {
            "instructions": [
                "Listen to musical examples featuring 4/4, 3/4, and 6/8 time and direct students to move to the beat.",
                "Review time signatures and note values using the worksheets below. Download Teacher Worksheet (PDF)",
                "As a class, create several examples of 4/4, 3/4, and/or 6/8 rhythmic patterns by getting suggestions from individual students. Write out each pattern on the board and then practice clapping and repeating each rhythm.",
                "Have students work in small groups to compose their own 4/4, 3/4, or 6/8 measures by completing the Student Worksheet below. Invite students to teach their rhythms to the class. Download Student Worksheet (PDF)"
            ],
            "goingDeeper": [
                "Have each small group add body percussion to their rhythms (e.g., snap for quarter-notes, pat shoulders for eighth-notes, etc.).",
                "Try clapping all of the newly composed 4/4, 3/4, or 6/8 measures in a row without repeats. Decide on an order that seems the most interesting and musically rich.",
                "Have students add pitches to their rhythms to create melodic compositions."
            ]
        },
        "resources": {
            "worksheets": [
                {
                    "title": "Download Teacher Worksheet (PDF)",
                    "url": "https://www.carnegiehall.org/-/media/CarnegieHall/Files/PDFs/Education/Educators/Toolbox/Grade-3/Toolbox-Grade-3-Composing-in-Simple-and-Compound-Meters-Activity-Key.pdf?la=en&hash=296B7AB68687C4B8039425020248BABB"
                },
                {
                    "title": "Download Student Worksheet (PDF)",
                    "url": "https://www.carnegiehall.org/-/media/CarnegieHall/Files/PDFs/Education/Educators/Toolbox/Grade-3/Toolbox-Grade-3-Composing-in-Simple-and-Compound-Meters-Composing.pdf?la=en&hash=E555E8F8CC85D9C56125FDE0A518390D"
                }
            ],
            "assessments": [
                {
                    "title": "3rd Grade Formative Assessment: Rhythm & Meter (PDF)",
                    "url": "https://www.carnegiehall.org/-/media/CarnegieHall/Files/PDFs/Education/Educators/Toolbox/Grade-3/Toolbox-Grade-3-Formative-Assessment-Rhythm-and-Meter.pdf?la=en",
                    "image": "https://carnegiehall.imgix.net/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Formative-Assessment-Rhythm-and-Meter-N-UP.jpg?w=301&h=406&fit=crop&crop=faces",
                    "alt": "Rhythm and Meter student worksheet"
                },
                {
                    "title": "3rd Grade Formative Assessment: Form (PDF)",
                    "url": "https://www.carnegiehall.org/-/media/CarnegieHall/Files/PDFs/Education/Educators/Toolbox/Grade-3/Toolbox-Grade-3-Formative-Assessment-Form-and-Design.pdf?la=en",
                    "image": "https://carnegiehall.imgix.net/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Formative-Assessment-Form-and-Design-N-UP.jpg?w=301&h=406&fit=crop&crop=faces",
                    "alt": "Form and Design student worksheet"
                },
                {
                    "title": "3rd Grade Summative Assessment (PDF)",
                    "url": "https://www.carnegiehall.org/-/media/CarnegieHall/Files/PDFs/Education/Educators/Toolbox/Grade-3/Toolbox-Grade-3-Summative-Assessment.pdf?la=en",
                    "image": "https://carnegiehall.imgix.net/-/media/CarnegieHall/Images/Education/Music-Educators-Toolbox/Grade-3/Summative-Assessment-N-UP.jpg?w=301&h=406&fit=crop&crop=faces",
                    "alt": "Summative Assessment Teacher Worksheet table of contents with scope of musical concepts"
                }
            ]
        },
        "videos": [
            {
                "title": "Grade 3 Activity Demo: Rhythm and Meter",
                "vimeoId": "111863545",
                "image": "https://carnegiehall.imgix.net/-/media/Feature/BrightCove/Import-Images/Composing-in-Simple-and-Compound-Meters-Rhythm-and-Meter-Activity.jpeg?w=1920&h=1080",
                "summary": "Carnegie Hall demo: \u201cCompose in Simple and Compound Meters.\u201d Students compose and notate short rhythms."
            },
            {
                "title": "Grade 3 Summative Assessment Demo: Rhythm and Meter",
                "vimeoId": "111863923",
                "image": "https://carnegiehall.imgix.net/-/media/Feature/BrightCove/Import-Images/Composing-in-Simple-and-Compound-Meters-Rhythm-and-Meter-Summative-Assessment.jpeg?w=1920&h=1080",
                "summary": "Carnegie Hall demo: \u201cImprovise a Rhythm.\u201d Students take turns improvising a one-measure rhythm to demonstrate phrase length, fluid rhythms, and a steady beat."
            },
            {
                "title": "Grade 3 Summative Assessment Demo: Rhythm and Meter",
                "vimeoId": "111864237",
                "image": "https://carnegiehall.imgix.net/-/media/Feature/BrightCove/Import-Images/Composing-in-Simple-and-Compound-Meters-Rhythm-and-Meter-Summative-Assessment-2.jpeg?w=1920&h=1080",
                "summary": "Carnegie Hall demo: \u201cTranscribe a Rhythm.\u201d Students listen to a two-measure rhythmic phrase and transcribe it using the Student Worksheet."
            }
        ],
        "rules": [
            {
                "id": "meters-base",
                "materials": [
                    "Rhythm cards",
                    "Meter cards for 4/4, 3/4, and 6/8",
                    "Role cards for composer, performer, conductor, notator, and arranger"
                ],
                "setup": [
                    "Show sound, movement, pictures, words, and notation as different ways to share rhythm."
                ],
                "participation": [
                    "Clap or tap",
                    "Move silently",
                    "Arrange rhythm cards",
                    "Conduct dynamics",
                    "Ask a partner to perform a rhythm"
                ],
                "always": true
            },
            {
                "id": "meters-silent",
                "materials": [
                    "Metronome or soft pulse track",
                    "Silent gesture menu",
                    "Quiet percussion choices"
                ],
                "setup": [
                    "Begin with a silent round. Add quiet sound once the rhythm feels steady."
                ],
                "participation": [
                    "Perform with hand signs or body gestures",
                    "Conduct silent dynamics",
                    "Use soft instruments or desk taps"
                ],
                "stepNotes": {
                    "0": [
                        "Listen first, then move to the beat silently before adding classroom sound."
                    ],
                    "2": [
                        "Try each rhythm silently, softly, and then at performance volume."
                    ],
                    "3": [
                        "Groups may share silently, quietly, or through a partner performer."
                    ]
                },
                "tools": [
                    "quiet-percussion",
                    "metronome",
                    "headphones",
                    "no-tech"
                ],
                "needs": [
                    "sound-sensitivity",
                    "attention-focus",
                    "working-memory"
                ]
            },
            {
                "id": "meters-motor",
                "materials": [
                    "Adaptive switch",
                    "Tablet tap pad",
                    "Large rhythm cards",
                    "Single-button beat trigger",
                    "Icon rhythm cards"
                ],
                "setup": [
                    "Provide one input that can show beats without handwriting a full rhythm. Cards, icons, switches, and tapping all count."
                ],
                "participation": [
                    "Trigger beats with a switch",
                    "Arrange rhythm cards",
                    "Direct a partner performer",
                    "Use pointing, eye gaze, or yes/no choices"
                ],
                "stepNotes": {
                    "2": [
                        "Students can suggest rhythms by tapping, choosing cards, or selecting from projected options."
                    ],
                    "3": [
                        "Groups may compose with cards or a tablet instead of handwriting the whole measure."
                    ]
                },
                "tools": [
                    "adaptive-switches",
                    "tablet",
                    "visual-cards"
                ],
                "needs": [
                    "motor-access",
                    "nonverbal-options",
                    "notation-difficulty"
                ]
            },
            {
                "id": "meters-projection",
                "materials": [
                    "Projected rhythm grid",
                    "Visual or word-based notation key",
                    "Meter templates",
                    "Icon rhythm cards"
                ],
                "setup": [
                    "Show a rhythm grid with beat spaces. Let students use visual or icon notation before they switch to standard notation."
                ],
                "participation": [
                    "Point to rhythm symbols",
                    "Use syllables or icons before standard notation",
                    "Follow the projected beat grid while performing"
                ],
                "stepNotes": {
                    "1": [
                        "Match note values to pictures, rhythm words, or icon cards before using standard notation."
                    ],
                    "2": [
                        "Build class rhythms on the grid and say how each beat is filled."
                    ],
                    "3": [
                        "Groups can share a card or projected rhythm instead of only a worksheet.",
                        "If notation is tricky, groups can submit an icon rhythm and then translate one part into standard notation together."
                    ]
                },
                "tools": [
                    "projector",
                    "tablet",
                    "visual-cards"
                ],
                "needs": [
                    "notation-difficulty",
                    "working-memory",
                    "attention-focus"
                ]
            },
            {
                "id": "meters-social-choice",
                "materials": [
                    "Two-choice role cards",
                    "Group practice checklist"
                ],
                "setup": [
                    "Give each group a short role menu and time to practice before sharing."
                ],
                "participation": [
                    "Teach by conducting",
                    "Have another student perform the rhythm",
                    "Share a visual rhythm"
                ],
                "stepNotes": {
                    "3": [
                        "Before sharing, groups choose one path: perform, conduct, or display and count."
                    ]
                },
                "tools": [
                    "small-groups",
                    "visual-cards",
                    "no-tech"
                ],
                "needs": [
                    "social-exposure",
                    "choice-overload",
                    "group-pacing"
                ]
            },
            {
                "id": "meters-extension",
                "materials": [
                    "Class-picked syllable set or icon set",
                    "Optional pitch cards"
                ],
                "setup": [
                    "Offer a small notation menu. Let the class pick the rhythm language for the day."
                ],
                "participation": [
                    "Translate rhythm between syllables, icons, body percussion, and notation",
                    "Add pitches after the rhythm is steady"
                ],
                "stepNotes": {
                    "2": [
                        "Let the class pick a syllable or icon language, then stick with it."
                    ],
                    "4": [
                        "Add pitches only after the rhythm is steady and easy to read."
                    ]
                },
                "tools": [
                    "preferred-music",
                    "visual-cards"
                ],
                "needs": [
                    "attention-focus",
                    "challenge-extension",
                    "notation-difficulty"
                ]
            },
            {
                "id": "meters-floor-grid",
                "materials": [
                    "Floor beat grid",
                    "Meter cards for 4/4, 3/4, and 6/8",
                    "Large rhythm cards"
                ],
                "setup": [
                    "Put beat spaces on the floor or on desks. Students can step, point, or place cards into the meter."
                ],
                "participation": [
                    "Step the beat spaces",
                    "Place cards on the floor grid",
                    "Point while a partner performs"
                ],
                "stepNotes": {
                    "0": [
                        "Students can move to the beat by stepping the floor grid, tapping from a seat, or pointing to beat spaces."
                    ],
                    "2": [
                        "Build one class rhythm on the floor grid before writing it on the board."
                    ],
                    "3": [
                        "Groups can compose by placing cards into a floor or desk grid, then perform or ask a partner to perform it."
                    ]
                },
                "tools": [
                    "floor-space",
                    "visual-cards",
                    "no-tech"
                ],
                "needs": [
                    "notation-difficulty",
                    "motor-access",
                    "attention-focus",
                    "working-memory",
                    "group-pacing"
                ]
            }
        ]
    }
];

    var selectedActivity = "score-on-the-floor";
    var selectedTools = [];
    var selectedNeeds = [];

    function q(selector) { return document.querySelector(selector); }
    function qa(selector) { return Array.prototype.slice.call(document.querySelectorAll(selector)); }

    function clean(text) {
      var div = document.createElement("div");
      div.textContent = text == null ? "" : String(text);
      return div.innerHTML;
    }

    function currentActivity() {
      for (var i = 0; i < activities.length; i++) {
        if (activities[i].id === selectedActivity) { return activities[i]; }
      }
      return activities[0];
    }

    function has(list, value) { return list.indexOf(value) > -1; }

    function toggle(list, value) {
      var spot = list.indexOf(value);
      if (spot > -1) { list.splice(spot, 1); }
      else { list.push(value); }
    }

    function unique(items) {
      var out = [];
      for (var i = 0; i < items.length; i++) {
        if (items[i] && out.indexOf(items[i]) === -1) { out.push(items[i]); }
      }
      return out;
    }

    function list(items, className) {
      if (!items || !items.length) { return ""; }
      var html = '<ul' + (className ? ' class="' + className + '"' : '') + '>';
      for (var i = 0; i < items.length; i++) { html += '<li>' + clean(items[i]) + '</li>'; }
      return html + '</ul>';
    }

    function overlaps(selected, allowed) {
      if (!allowed || !allowed.length) { return false; }
      for (var i = 0; i < selected.length; i++) {
        if (has(allowed, selected[i])) { return true; }
      }
      return false;
    }

    function ruleWorks(rule) {
      if (rule.always) { return true; }
      return overlaps(selectedTools, rule.tools) && overlaps(selectedNeeds, rule.needs);
    }

    function activeRules(activity) {
      var rules = [];
      for (var i = 0; i < activity.rules.length; i++) {
        if (ruleWorks(activity.rules[i])) { rules.push(activity.rules[i]); }
      }
      return rules;
    }

    function simpleStep(text) {
      return String(text || "")
        .replace(/Download Teacher Worksheet \(PDF\)/g, "Use the teacher worksheet if helpful.")
        .replace(/Download Student Worksheet \(PDF\)/g, "Use the student worksheet if helpful.");
    }

    function drawStep(text, number, rules) {
      var notes = [];
      for (var i = 0; i < rules.length; i++) {
        var add = rules[i].stepNotes && rules[i].stepNotes[String(number)];
        if (add) { notes = notes.concat(add); }
      }
      notes = unique(notes);
      var html = '<div class="step"><div><span class="number">' + (number + 1) + '</span></div><div>';
      html += '<p>' + clean(simpleStep(text)) + '</p>';
      if (notes.length) { html += '<p class="add"><b>Add:</b> ' + clean(notes.join(" ")) + '</p>'; }
      return html + '</div></div>';
    }

    function drawPlan() {
      var activity = currentActivity();
      var rules = activeRules(activity);
      var materials = activity.baseMaterials.slice();
      var setup = [];
      var ways = [];
      for (var i = 0; i < rules.length; i++) {
        materials = materials.concat(rules[i].materials || []);
        setup = setup.concat(rules[i].setup || []);
        ways = ways.concat(rules[i].participation || []);
      }
      materials = unique(materials);
      setup = unique(setup);
      ways = unique(ways);
      if (!setup.length) { setup = ["Use the original setup. Before you start, show students the ways they can join."]; }
      if (!ways.length) { ways = ["Move", "Point", "Choose a card", "Conduct", "Direct a partner"]; }

      var html = '<div class="lesson-head">';
      html += '<img src="' + activity.heroImage + '" alt="' + clean(activity.title) + '">';
      html += '<div><p class="small-title">Ready to teach</p><h2>' + clean(activity.title) + '</h2>';
      html += '<p class="muted">' + clean(activity.metadata.summary) + '</p>';
      html += '<div class="details"><p class="detail"><span>Goal</span><b>' + clean(activity.metadata.aim) + '</b></p>';
      html += '<p class="detail"><span>Focus</span><b>' + clean(activity.metadata.concept) + '</b></p></div></div></div>';

      html += '<div class="stack">';
      html += '<div class="box"><h3>Materials</h3>' + list(materials) + '</div>';
      html += '<div class="box"><h3>Set it up</h3>' + list(setup) + '<h3>Ways students can join</h3>' + list(ways, "ways") + '</div>';
      html += '<div class="box"><h3>Steps</h3>';
      for (var step = 0; step < activity.original.instructions.length; step++) {
        html += drawStep(activity.original.instructions[step], step, rules);
      }
      html += '</div>';
      if (activity.original.goingDeeper && activity.original.goingDeeper.length) {
        html += '<div class="box"><h3>Keep going</h3>' + list(activity.original.goingDeeper) + '</div>';
      }
      html += '<div class="box"><h3>Source</h3><p><a href="' + activity.sourceUrl + '" target="_blank" rel="noopener">Open the Carnegie Hall activity page</a></p></div>';
      html += '</div>';
      q("#plan").innerHTML = html;
    }

    function mediaCard(title, text, image, url, label) {
      var html = '<div class="media-card">';
      if (image) { html += '<img src="' + image + '" alt="' + clean(title) + '">'; }
      html += '<div><h4>' + clean(title) + '</h4>';
      if (text) { html += '<p class="muted">' + clean(text) + '</p>'; }
      html += '<p><a href="' + url + '" target="_blank" rel="noopener">' + label + '</a></p></div></div>';
      return html;
    }

    function drawLinks() {
      var activity = currentActivity();
      var cards = [];
      for (var i = 0; i < activity.videos.length; i++) {
        var video = activity.videos[i];
        cards.push(mediaCard(video.title, video.summary, video.image, "https://vimeo.com/" + video.vimeoId, "Watch video"));
      }
      var worksheets = activity.resources.worksheets || [];
      var assessments = activity.resources.assessments || [];
      var resources = worksheets.concat(assessments);
      for (var r = 0; r < resources.length; r++) {
        var item = resources[r];
        cards.push(mediaCard(item.title, "", item.image, item.url, "Open PDF"));
      }
      q("#links").innerHTML = '<div class="box"><div class="media-grid">' + cards.join("") + '</div></div>';
    }

    function setButtons() {
      qa("[data-activity]").forEach(function(button) {
        button.classList.toggle("selected", button.getAttribute("data-activity") === selectedActivity);
      });
      qa("[data-kind]").forEach(function(button) {
        var kind = button.getAttribute("data-kind");
        var id = button.getAttribute("data-id");
        var on = kind === "tool" ? has(selectedTools, id) : has(selectedNeeds, id);
        button.classList.toggle("selected", on);
      });
    }

    function redraw() {
      setButtons();
      drawPlan();
      drawLinks();
    }

    qa("[data-activity]").forEach(function(button) {
      button.onclick = function() {
        selectedActivity = this.getAttribute("data-activity");
        redraw();
        q("#customize").scrollIntoView();
      };
    });

    qa("[data-kind]").forEach(function(button) {
      button.onclick = function() {
        var kind = this.getAttribute("data-kind");
        var id = this.getAttribute("data-id");
        toggle(kind === "tool" ? selectedTools : selectedNeeds, id);
        redraw();
      };
    });

    q("#clearTools").onclick = function() { selectedTools = []; redraw(); };
    q("#clearNeeds").onclick = function() { selectedNeeds = []; redraw(); };

    redraw();
  </script>
</body>
</html>
