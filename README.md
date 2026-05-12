package com.example.lifehackapp

import android.content.Intent
import android.os.Bundle
import android.widget.Button
import androidx.appcompat.app.AppCompatActivity

class WelcomeActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        // Connect XML
        setContentView(R.layout.activity_welcome)

        // Button
        val startBtn = findViewById<Button>(R.id.startBtn)

        // Click action
        startBtn.setOnClickListener {
            val intent = Intent(this, QuestionActivity::class.java)
            startActivity(intent)
        }
    }
}

package com.example.lifehackapp

import android.content.Intent
import android.os.Bundle
import android.widget.*
import androidx.appcompat.app.AppCompatActivity

class ScoreActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_score)

        val scoreText = findViewById<TextView>(R.id.scoreText)
        val messageText = findViewById<TextView>(R.id.messageText)
        val reviewBtn = findViewById<Button>(R.id.reviewBtn)
        val restartBtn = findViewById<Button>(R.id.restartBtn)

        val score = intent.getIntExtra("SCORE", 0)
        val total = intent.getIntExtra("TOTAL", 0)

        scoreText.text = "Score: $score / $total"

        if (score == total) {
            messageText.text = "🔥 Perfect!"
        } else if (score >= total / 2) {
            messageText.text = "👍 Good job!"
        } else {
            messageText.text = "⚠️ Try again!"
        }

        reviewBtn.setOnClickListener {
            val intent = Intent(this, ReviewActivity::class.java)
            intent.putExtra("QUESTIONS", intent.getStringArrayExtra("QUESTIONS"))
            intent.putExtra("ANSWERS", intent.getBooleanArrayExtra("ANSWERS"))
            startActivity(intent)
        }

        restartBtn.setOnClickListener {
            val intent = Intent(this, WelcomeActivity::class.java)
            startActivity(intent)
        }
    }
}

package com.example.lifehackapp

import android.content.Intent
import android.os.Bundle
import android.widget.*
import androidx.appcompat.app.AppCompatActivity

class ScoreActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_score)

        val scoreText = findViewById<TextView>(R.id.scoreText)
        val messageText = findViewById<TextView>(R.id.messageText)
        val reviewBtn = findViewById<Button>(R.id.reviewBtn)
        val restartBtn = findViewById<Button>(R.id.restartBtn)

        val score = intent.getIntExtra("SCORE", 0)
        val total = intent.getIntExtra("TOTAL", 0)

        scoreText.text = "Score: $score / $total"

        if (score == total) {
            messageText.text = "🔥 Perfect!"
        } else if (score >= total / 2) {
            messageText.text = "👍 Good job!"
        } else {
            messageText.text = "⚠️ Try again!"
        }

        reviewBtn.setOnClickListener {
            val intent = Intent(this, ReviewActivity::class.java)
            intent.putExtra("QUESTIONS", intent.getStringArrayExtra("QUESTIONS"))
            intent.putExtra("ANSWERS", intent.getBooleanArrayExtra("ANSWERS"))
            startActivity(intent)
        }

        restartBtn.setOnClickListener {
            val intent = Intent(this, WelcomeActivity::class.java)
            startActivity(intent)
        }
    }
}

package com.example.lifehackapp

import android.content.Intent
import android.os.Bundle
import android.widget.Button
import androidx.appcompat.app.AppCompatActivity

class WelcomeActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        // Connect XML
        setContentView(R.layout.activity_welcome)

        // Button
        val startBtn = findViewById<Button>(R.id.startBtn)

        // Click action
        startBtn.setOnClickListener {
            val intent = Intent(this, QuestionActivity::class.java)
            startActivity(intent)
        }
    }
}

