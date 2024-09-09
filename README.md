import React, { useState, useEffect, useRef } from "react";

const Proposal: React.FC = () => {
  const [showFinalMessage, setShowFinalMessage] = useState(false);
  const [hovering, setHovering] = useState(false);
  const audioRef = useRef<HTMLAudioElement>(null);

  const handleNoHover = () => {
    setHovering(!hovering);
  };

  const handleYesClick = () => {
    setShowFinalMessage(true);
    if (audioRef.current) {
      audioRef.current.play().catch((error) => {
        console.error("Audio playback error:", error);
      });
    }
  };

  useEffect(() => {
    if (showFinalMessage && audioRef.current) {
      audioRef.current.play().catch((error) => {
        console.error("Audio playback error:", error);
      });
    }
  }, [showFinalMessage]);

  return (
    <div style={{ textAlign: "center", marginTop: "100px" }}>
      <h1>Samahan mo ko sa Balik Sinta?</h1>
      {showFinalMessage ? (
        <div>
          <h2>Yay! Sama tayo!</h2>
          <img
            src="https://media.giphy.com/media/vtm4qejJIl1ERPIrbA/giphy.gif?cid=790b761161qbveksnfz3j3d8jybu4g8lo3najnw5i6i7tatv&ep=v1_gifs_search&rid=giphy.gif&ct=g"
            alt="Kinikilig"
            style={{ width: "300px", height: "300px" }}
          />
          <audio ref={audioRef} controls autoPlay>
            <source
              src="https://www.dropbox.com/scl/fi/p0b33ukgy9x8fg0ken1lv/James-Reid-and-Nadine-Lustre-Hanap-Hanap-Lyric-Video-with-Chords.mp3?rlkey=civw7lj94doubszp9svky8zxy&raw=1"
              type="audio/mpeg"
            />
            Your browser does not support the audio element.
          </audio>
        </div>
      ) : (
        <div>
          <button
            style={{ margin: "10px", padding: "10px", fontSize: "18px" }}
            onClick={handleYesClick}
          >
            Oo
          </button>
          <button
            id="noButton"
            style={{
              margin: "10px",
              padding: "10px",
              fontSize: "18px",
              position: "relative",
            }}
            onMouseEnter={handleNoHover}
          >
            Hindi
          </button>
        </div>
      )}
    </div>
  );
};

export default Proposal;
